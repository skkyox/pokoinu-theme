# 🐾 Pokoinu — Thème Shopify

Code source du thème de la boutique [pokoinu.myshopify.com](https://pokoinu.myshopify.com).
Thème de base : **Horizon** (thème par défaut de Shopify).

> Ce README est écrit pour des débutants. Suivez-le pas à pas, il est fait pour être reproductible.

---

## 🧰 Prérequis (à installer une seule fois)

| Outil | Vérifier avec | Pour quoi faire |
|---|---|---|
| [Node.js](https://nodejs.org) (v18+) | `node --version` | Faire tourner les outils (lint, hooks) |
| [Git](https://git-scm.com) | `git --version` | Versionner le code |
| [Shopify CLI](https://shopify.dev/docs/themes/tools/cli) | `shopify version` | Développer et déployer le thème |

Installer le Shopify CLI si besoin :

```bash
npm install -g @shopify/cli@latest
```

---

## 🚀 Démarrer en local

```bash
# 1. Récupérer le projet
git clone <url-du-repo>
cd pokoinu

# 2. Installer les outils de qualité (lint + hooks Git)
npm install

# 3. Lancer le serveur de développement avec live reload
shopify theme dev --store pokoinu.myshopify.com
```

Ouvre ensuite **http://127.0.0.1:9292**. Chaque fois que tu **sauvegardes** un fichier,
la page se rafraîchit toute seule. Rien n'est envoyé à la boutique en ligne : c'est un
**bac à sable local**. Pour arrêter : `Ctrl + C`.

---

## 🌳 Stratégie de branches

On garde volontairement quelque chose de **simple** :

| Branche | Rôle | Thème Shopify associé |
|---|---|---|
| `main` | **Production** — ce que voient les vrais clients | Thème **publié** |
| `staging` | **Préproduction** — pour tester avant de publier | Thème **non publié** (aperçu) |

> On ne travaille (presque) jamais directement sur `main`. On teste sur `staging`,
> et quand c'est bon, on fusionne dans `main`.

### Le cycle de travail au quotidien

```bash
# Partir de staging à jour
git checkout staging
git pull

# Faire tes modifs, puis les enregistrer
git add .
git commit -m "Décris ta modif (ex: change la couleur du bouton panier)"

# Envoyer sur GitHub → déclenche un déploiement AUTO vers le thème de test
git push
```

1. Tu vérifies le rendu sur le **thème de préproduction** (aperçu, non publié).
2. Quand tout est bon, tu passes en production via une **Pull Request** `staging → main` :

```bash
# Créer la Pull Request (ouvre GitHub dans le navigateur)
gh pr create --base main --head staging --fill
```

3. Tu fusionnes la PR sur GitHub → déploiement **AUTO** vers le thème publié. 🎉

---

## 🔍 Qualité du code

- **Theme Check** (le linter officiel Shopify) analyse le code à la recherche d'erreurs
  et de mauvaises pratiques.
- Un **hook pre-commit** lance Theme Check **automatiquement avant chaque commit**.
  Si le code a des erreurs, le commit est **bloqué** tant que ce n'est pas corrigé.

Lancer le linter à la main quand tu veux :

```bash
shopify theme check
```

---

## 🤖 Déploiement automatique (CI/CD)

Géré par **GitHub Actions** (gratuit). Aucun déploiement manuel n'est nécessaire :

| Évènement | Action automatique |
|---|---|
| `push` sur `staging` | Theme Check, puis **push** vers le thème de préproduction (non publié) |
| Fusion (merge) sur `main` | Theme Check, puis **déploiement** vers le thème publié (production) |

Si Theme Check échoue, le déploiement est **bloqué**.

> 🔐 Le déploiement utilise un **Theme Access token** stocké dans les *Secrets* GitHub
> (jamais dans le code). Voir la section suivante.

---

## 🔐 Le token de déploiement (à créer une fois)

Le robot GitHub a besoin d'un mot de passe pour parler à Shopify : le **Theme Access token**.

1. Dans l'admin Shopify, installe l'app gratuite **Theme Access**
   (`Apps` → rechercher « Theme Access » → installer).
2. Crée un accès, indique ton email, tu reçois un **token** qui commence par `shptka_...`.
3. Sur GitHub : `Settings` du repo → `Secrets and variables` → `Actions` → `New repository secret`.
   - Nom : `SHOPIFY_CLI_THEME_TOKEN`
   - Valeur : le token `shptka_...`
4. Ajoute un second secret :
   - Nom : `SHOPIFY_STORE`
   - Valeur : `pokoinu.myshopify.com`

⚠️ **Ne colle JAMAIS ce token dans un fichier du repo.** S'il fuite, révoque-le dans l'app
Theme Access et recrée-en un.

---

## 📁 Structure d'un thème Shopify

| Dossier | Contenu |
|---|---|
| `layout/` | Squelette HTML global (`theme.liquid`) |
| `templates/` | Gabarits de page (accueil, produit, panier…) |
| `sections/` | Grands blocs de page réutilisables |
| `blocks/` | Briques imbriquables (spécifique à Horizon) |
| `snippets/` | Petits bouts de code Liquid réutilisés |
| `assets/` | CSS, JavaScript, images, polices |
| `locales/` | Traductions (textes multilingues) |
| `config/` | Réglages du thème |
