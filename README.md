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

# Envoyer sur GitHub → Shopify met à jour le thème de test tout seul
git push
```

1. Tu vérifies le rendu sur le **thème de préproduction** (brouillon connecté à `staging`).
2. Quand tout est bon, tu passes en production via une **Pull Request** `staging → main` :

```bash
# Créer la Pull Request (ouvre GitHub dans le navigateur)
gh pr create --base main --head staging --fill
```

3. Tu fusionnes la PR sur GitHub → Shopify met à jour le **thème de prod** tout seul. 🎉

> Le déploiement est assuré par l'**intégration native Shopify ↔ GitHub** (voir plus bas) :
> pas de robot, pas de token, pas de commande. Un `git push` suffit.

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

## 🔗 Déploiement : intégration native Shopify ↔ GitHub

Le déploiement est géré par la **fonction intégrée de Shopify** (gratuite, sans token,
sans GitHub Actions). Chaque thème peut être **connecté à une branche** du dépôt :

| Branche GitHub | Thème Shopify connecté | Rôle |
|---|---|---|
| `main` | thème **« pokoinu-theme/main »** | Production (à **publier** quand prêt) |
| `staging` | *(optionnel)* un 2ᵉ thème brouillon | Préproduction / aperçu |

**Comment ça marche :**
- Tu pousses du code sur une branche (`git push`) → Shopify **met à jour le thème connecté
  automatiquement**.
- Tu modifies ce thème dans l'**éditeur Shopify** → Shopify **recommite les changements sur
  la branche**. La synchro va donc **dans les deux sens**.
- Un thème connecté reste en **brouillon** tant que tu ne cliques pas sur **Publish** :
  aucun risque de casser la boutique en ligne tant que tu n'as pas publié.

**Connecter une branche (une seule fois, dans l'admin) :**
`Boutique en ligne → Thèmes → Ajouter un thème → Connecter depuis GitHub`, puis choisis le
dépôt `pokoinu-theme` et la branche voulue (`main`, ou `staging`).

> 💡 Pas besoin de Theme Access token ni de secrets GitHub avec cette méthode.

---

## ✅ Mise en vente (admin Shopify)

La configuration de la boutique côté admin (paiements, pages légales, livraison, taxes,
apps) se fait **à la main**. Une checklist ordonnée par priorité est disponible ici :

👉 [`docs/checklist-mise-en-vente.md`](docs/checklist-mise-en-vente.md)

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
