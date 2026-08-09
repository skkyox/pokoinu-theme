# ✅ Checklist de mise en vente — Pokoinu

Checklist **ordonnée par priorité** pour finaliser la boutique à la main dans l'admin
Shopify. Coche au fur et à mesure. Fais les blocs **dans l'ordre** : le bloc 1 t'empêche
littéralement de vendre tant qu'il n'est pas fait.

> ⚠️ **Avertissement.** Ce document est une aide pratique pour débutants, **pas un conseil
> juridique ni fiscal**. Les obligations légales françaises évoluent : vérifie sur
> [service-public.fr](https://entreprendre.service-public.fr) et
> [economie.gouv.fr](https://www.economie.gouv.fr), ou auprès d'un professionnel.

> 💸 **« Budget zéro » : la vérité.** Les *apps* proposées ici sont gratuites, mais **vendre
> sur Shopify n'est pas gratuit**. Coûts incompressibles à prévoir :
> - **Abonnement Shopify** (souvent une offre d'essai à ~1 €/mois les 3 premiers mois, puis
>   le plan Basic mensuel).
> - **Frais de transaction** sur chaque vente (le processeur de paiement se rémunère ici).
> - **Statut juridique** : pour encaisser proprement, il te faut en pratique une
>   **micro-entreprise** (création gratuite en ligne, sous 15 min) → tu obtiens un **SIRET**,
>   indispensable pour Shopify Payments et pour tes mentions légales.

---

## 🟥 BLOC 1 — BLOQUANT : sans ça, tu ne peux pas encaisser

- [ ] **Créer ta micro-entreprise et obtenir un SIRET**
  *Pourquoi :* obligatoire pour être payé (Shopify Payments le demande) et pour tes pages
  légales. *Où :* [formalites.entreprises.gouv.fr](https://formalites.entreprises.gouv.fr)
  (gratuit). Choisis l'activité « commerce de détail / vente à distance ».

- [ ] **Ouvrir un compte bancaire pro (ou dédié)** pour recevoir les paiements.
  *Astuce gratuite :* un compte en ligne gratuit type Revolut/Shine/Qonto (offres de base)
  suffit pour démarrer. Il te faut un **IBAN**.

- [ ] **Activer un moyen de paiement principal : Shopify Payments**
  *Où :* `Paramètres → Paiements → Activer Shopify Payments`.
  *Ce qu'il demande :* SIRET, adresse, pièce d'identité, IBAN.
  > ℹ️ En France, **« Stripe » n'apparaît pas comme option séparée** : Shopify Payments
  > **est** propulsé par Stripe. Tu n'as donc pas à installer Stripe à part.

- [ ] **Ajouter PayPal comme 2ᵉ moyen de paiement**
  *Pourquoi :* rassure fortement les acheteurs venus de TikTok (public jeune, méfiant).
  *Où :* `Paramètres → Paiements → Ajouter des méthodes → PayPal`. Un compte PayPal (perso
  au début) suffit à activer.

- [ ] **Faire une commande-test réelle** (petit montant) pour vérifier que le paiement
  passe et que la commande arrive bien. Rembourse-toi ensuite.

---

## 🟧 BLOC 2 — OBLIGATOIRE LÉGALEMENT (avant d'ouvrir au public)

Shopify génère des **modèles** de pages : `Paramètres → Politiques` (bouton
« Créer à partir d'un modèle »). ⚠️ **Les modèles ne suffisent pas** : tu dois les adapter
(surtout les délais de livraison — voir Bloc 3).

- [ ] **Mentions légales** *(page à créer)*
  Identité (nom, statut micro-entreprise), **SIRET**, adresse, email de contact,
  et l'**hébergeur** (Shopify Inc., adresse au Canada — dispo en ligne).
  *Où :* `Boutique en ligne → Pages → Ajouter une page`.

- [ ] **Conditions Générales de Vente (CGV)** — obligatoires en B2C.
  *Où :* `Paramètres → Politiques → Conditions générales`.

- [ ] **Politique de confidentialité (RGPD)** — comment tu collectes/utilises les données.
  *Où :* `Paramètres → Politiques → Politique de confidentialité`.

- [ ] **Politique de remboursement + droit de rétractation 14 jours**
  *Pourquoi :* en France, le client a **14 jours** pour se rétracter (vente à distance).
  *Où :* `Paramètres → Politiques → Politique de remboursement`.

- [ ] **Politique d'expédition / livraison** *(critique en dropshipping — voir Bloc 3)*
  *Où :* `Paramètres → Politiques → Politique d'expédition`.

- [ ] **Médiateur de la consommation** — la loi t'oblige à en proposer un et à afficher ses
  coordonnées (souvent dans les mentions légales/CGV). *Astuce :* plusieurs médiateurs
  proposent un abonnement, prévois-le (petit coût annuel).

- [ ] **Bannière cookies / consentement (RGPD-CNIL)**
  *Pourquoi :* obligatoire dès que tu poses un pixel de suivi (TikTok, analytics).
  *Où (gratuit) :* `Paramètres → Confidentialité du client → Bannière de cookies` (natif
  Shopify, gratuit). Active-la et configure la région **Europe**.

- [ ] **Lier ces pages dans le menu du bas (footer)**
  *Où :* `Boutique en ligne → Navigation → Menu de bas de page`. Un footer complet =
  gage de sérieux pour un trafic froid TikTok.

---

## 🟨 BLOC 3 — CONFIGURATION COMMERCIALE

- [ ] **TVA / Taxes**
  *Cas le plus courant au démarrage :* micro-entreprise **sous les seuils** = **franchise
  en base de TVA** → tu **ne factures pas** la TVA. Mention obligatoire sur les factures :
  *« TVA non applicable – art. 293 B du CGI »*.
  *Où :* `Paramètres → Taxes et droits` → configure pour ne pas ajouter de TVA tant que tu
  es en franchise. (Si un jour tu dépasses les seuils, il faudra l'activer.)

- [ ] **Délais de livraison affichés honnêtement**
  *Pourquoi :* en dropshipping, les colis (souvent d'Asie) mettent **1 à 4 semaines**.
  La loi t'oblige à informer le client du délai **avant** l'achat. Cacher un long délai =
  litiges, remboursements PayPal, et blocage possible des paiements.
  *À faire :* écris clairement le délai dans la **politique d'expédition** ET sur les
  **fiches produit**.

- [ ] **Zones et tarifs de livraison**
  *Où :* `Paramètres → Expéditions et livraisons`. Définis au moins la **France** (et
  l'Europe si tu veux). *Stratégie simple :* « livraison gratuite » avec le coût déjà
  intégré dans le prix produit.

- [ ] **Coordonnées & identité de la boutique**
  *Où :* `Paramètres → Détails de la boutique` : nom, email pro de contact, adresse,
  devise **EUR**.

- [ ] **Emails de notification** (confirmation de commande, expédition) — vérifie qu'ils
  partent bien et mets ton logo. *Où :* `Paramètres → Notifications`.

---

## 🟩 BLOC 4 — APPS ESSENTIELLES (100 % gratuites pour démarrer)

- [ ] **Sourcing & traitement des commandes : DSers** *(plan gratuit)*
  *Pourquoi :* relie tes produits AliExpress et permet de passer les commandes fournisseur
  en 1 clic quand un client achète. Le plan gratuit suffit largement au début.
  *(AutoDS est très bien aussi mais payant — on garde DSers pour le budget zéro.)*

- [ ] **Suivi de commande : ParcelPanel ou 17TRACK** *(plan gratuit)*
  *Pourquoi :* une page « Suivre ma commande » rassure et réduit les emails « où est mon
  colis ? ». Les deux ont un palier gratuit (nombre de commandes/mois limité).

- [ ] **Avis produits : Judge.me** *(plan gratuit)*
  *Pourquoi :* un trafic froid TikTok convertit beaucoup mieux avec des avis visibles.

- [ ] **Canal TikTok : app TikTok pour Shopify** *(gratuit)*
  *Pourquoi :* même en organique, ça installe le **pixel** (mesure + retargeting plus tard)
  et facilite les liens produits. ⚠️ N'active le pixel **qu'après** la bannière cookies.

---

## 🟦 BLOC 5 — DERNIÈRES VÉRIFS AVANT LANCEMENT TIKTOK

- [ ] **Tout tester sur mobile** (le trafic TikTok est à ~95 % mobile) : navigation, fiche
  produit, ajout panier, paiement.
- [ ] **Email de panier abandonné** activé *(Paramètres → Notifications / Marketing)*.
- [ ] **Au moins 1 fiche produit vraiment soignée** : photos nettes, bénéfices clairs,
  avis, délai de livraison indiqué.
- [ ] **Retirer le mot de passe de la boutique** (elle devient publique)
  *Où :* `Boutique en ligne → Préférences → Protection par mot de passe` → décocher.
  👉 **À faire en TOUT DERNIER**, une fois les blocs 1-2-3 terminés.

---

### Ordre de priorité résumé
1. **Bloc 1** (encaisser) → **Bloc 2** (légal) → **Bloc 3** (config) : le **minimum pour
   ouvrir légalement**.
2. **Bloc 4** (apps) : à faire en parallèle, indispensable au dropshipping.
3. **Bloc 5** : juste avant d'envoyer le premier TikTok.
