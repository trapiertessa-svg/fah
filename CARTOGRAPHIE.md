# Cartographie — `particuliers.html`

Page « Ménage à domicile à Reims » de Feel at Home (audience **Particuliers**).
Fichier unique de 2 032 lignes : tout le CSS et le JS sont dans la page.
Les numéros de ligne renvoient à `particuliers.html` dans sa version actuelle. Ils bougent dès qu'on ajoute ou retire des lignes, donc cherchez plutôt par l'`id` ou la classe indiqués.

---

## 1. Vue d'ensemble du fichier

| Lignes | Bloc | Contenu |
|---|---|---|
| 1–20 | `<head>` : méta | Titre, description SEO, canonical, Open Graph, polices Google (Lustria + Inter) |
| 21–58 | JSON-LD (`schema.org/Service`) | Données structurées : société, téléphone, email, **les 2 offres et leurs prix** |
| 59 | Script Lucide | Bibliothèque d'icônes (`<i data-lucide="…">`) |
| 60–1222 | `<style>` | Tout le CSS (détail en §3) |
| 1223–1868 | `<body class="aud-part">` | Le contenu visible (détail en §2) |
| 1869–1946 | `<script>` n°1 | Burger, ticker, retour en haut, barre mobile, formulaire |
| 1947–2030 | `<script>` n°2 | Carrousel presse sur mobile (≤ 768 px) |

---

## 2. Sections visibles (dans l'ordre de la page)

| # | Section | Ancre / classe | HTML (lignes) | Ce qu'on y modifie |
|---|---|---|---|---|
| 0 | **Navigation** | `nav.nav` | 1227–1269 | Ticker défilant (1229–1238, les 4 messages sont **écrits 2 fois** pour la boucle), logo, liens menu (1241–1246), bascule Pro/Particulier, bouton Devis, menu mobile (1258–1267, **liste de liens en double**) |
| 1 | **Hero** | `section.hero` | 1272–1310 | Vidéo de fond (`assets/hero-video-particuliers.mp4`), badge Pépite, titre H1 (1283), sous-titre + « Reims et alentours » (1286), boutons Devis / WhatsApp (1287–1290), bandeau des 3 atouts `.hero-trust` (1293–1307) |
| 2 | **À propos / Elisa** | `#elisa` · `.about` | 1313–1359 | Citation d'Elisa (1319), médaille Pépite (1320–1326), photo (1330), bloc presse « Ils en ont parlé » `.fame-press` (1335–1356, 4 liens) |
| 3 | **Avantages** | `#avantages` · `.avantages` | 1362–1402 | Titre + 6 cartes `.avantage-card` (icône, titre, texte) |
| 4 | **Fonctionnement** | `#fonctionnement` · `.method` | 1405–1437 | 4 étapes `.step` (numéro, titre `h4`, texte) |
| 5 | **Formules / Tarifs** | `#offres` · `.pricing` | 1440–1489 | Carte « Feel at Home » (1449–1464), carte « Feel boost » (1466–1482), notes sous les cartes `.price-notes` (1485–1488) |
| 6 | **Crédit d'impôt** | `#credit-impot` · `.credit` | 1492–1511 | Texte explicatif, tableau d'exemple `.credit-demo` (1502–1507) |
| 7 | **Au quotidien** | `#quotidien` · `.pillars.quotidien` | 1514–1556 | 6 cartes `.pillar` (matériel, tâches, réclamation, annulation, jours fériés, absence) |
| 8 | **Zone d'intervention** | `#zone` · `.zone` | 1559–1623 | 4 zones avec prix et communes `.zone-item` (1571–1604), carte `images/carte-zones.jpg` (1610), **légende qui répète les 4 prix** (1613–1618) |
| 9 | **Avis clients** | `#avis` · `.testis.on-paper` | 1626–1754 | Citation, note 5,0 / 15 avis Google (1633), carrousel : 11 avis (1640–1694) **+ les mêmes 11 en double** (1695–1750, `aria-hidden`) pour la boucle infinie |
| 10 | **Contact / Devis** | `#contact` · `.contact` | 1757–1830 | Coordonnées (1766–1770), boutons WhatsApp / email / Instagram / LinkedIn (1771–1780), formulaire `#devis-form` (1787–1818), message de confirmation `#form-success` (1819–1823) |
| 11 | **Boutons flottants** | `.sticky-group` | 1833–1855 | Devis, WhatsApp, FAQ, retour en haut, bascule Pro/Perso |
| 12 | **Pied de page** | `footer` | 1857–1867 | Liens (Espace Pro, FAQ, Nos engagements, Mentions légales), copyright, CGV |

Couleurs de fond par section (pour s'y retrouver visuellement) : nav crème · hero vidéo · Elisa clair · **Avantages bleu foncé** · Fonctionnement clair · Formules clair · **Crédit d'impôt bleu foncé** · Au quotidien clair · Zone crème · Avis clair · **Contact bleu foncé** · footer foncé.

---

## 3. Carte du CSS (`<style>`, lignes 60–1222)

Le CSS vient de la page Pro (`index.html`) ; la page Particuliers y ajoute ses propres règles **à la fin** (lignes 1134–1221).

| Lignes | Rôle |
|---|---|
| 62–74 | **Variables `:root`** : couleurs, polices, arrondis, espacements. À modifier ici pour changer la charte partout |
| 75–89 | Base (reset, typo, titres) |
| 89–91 | `.container` (largeur max 1320 px), `.eyebrow` (petits surtitres) |
| 91–107 | Boutons `.btn-*` (primary, teal, yellow, line, wa, sm) |
| 109–115 | Ticker |
| 117–193 | Navigation, bascule audience |
| 195–258 | Hero (vidéo, titre, bande des 3 atouts) |
| 288–315 | Bandeau notoriété / presse (`.fame-*`) |
| 327–344 | Cartes `.pillar` (section « Au quotidien ») |
| 388–421 | Feuillages décoratifs en fond de section (SVG `assets/feuille-*.svg`) |
| 422–463 | Avantages |
| 486–547 | Tarifs `.price-*` |
| 572–623 | Fonctionnement (étapes) |
| 624–639 | À propos |
| 659–685 | Avis (carrousel) |
| 686–746 | Contact et formulaire |
| 747–786 | Boutons flottants |
| 787–802 | Footer |
| 803–840 | Burger mobile |
| 841–872 | Zone d'intervention |
| 873–924 | **Responsive tablette paysage** (≤ 1100 px) |
| 925–977 | **Responsive tablette portrait** (≤ 768 px) |
| 978–1128 | **Responsive mobile** (≤ 680 px) |
| 1129–1132 | Accessibilité : animations coupées si l'utilisateur les refuse |
| 1134–1221 | **Ajouts propres à la page Particuliers** : 4 étapes, notes tarifs, section crédit d'impôt, fond clair des avis, select du formulaire, liens du footer, + leurs règles responsive |

Variables principales :

| Variable | Valeur | Usage |
|---|---|---|
| `--ink` | `#13505C` | Bleu foncé : texte, fonds sombres |
| `--teal` | `#029DA4` | Bleu-vert d'accent |
| `--deep` | `#007588` | Bleu intermédiaire |
| `--yellow` | `#FEC700` | Jaune : boutons, mots en italique sur fond sombre |
| `--paper` | `#FBFAF6` | Fond clair |
| `--cream` | `#DBD8CE` | Fond crème |
| `--serif` / `--sans` | Lustria / Inter | Titres / texte |

**CSS hérité inutilisé sur cette page** (sans risque, mais alourdit le fichier) : `.case-*`, `.manifeste`, `.logos-*`, `.stats`, `.q-card`, `.av-panel-*`, `.prestas`, `.espace-*`, floor plan, bouton/panneau info.

---

## 4. JavaScript

| Lignes | Fonction | Rôle |
|---|---|---|
| 1870–1882 | (auto) | Liens Instagram/LinkedIn : ouvre l'appli sur mobile, le site sur ordinateur |
| 1884–1906 | `toggleNavMenu()` | Ouvre/ferme le menu burger (clic dehors et Échap le ferment) |
| 1908 | — | Dessine les icônes Lucide |
| 1910–1915 | (auto) | Affiche la flèche « retour en haut » après 400 px de défilement |
| 1917–1922 | (auto) | Cache le ticker dès qu'on défile |
| 1924–1937 | (auto) | Barre de boutons du bas (mobile) : transparente en descendant |
| 1939–1945 | `submitForm()` | **Formulaire de devis** : ouvre la messagerie avec un email pré-rempli vers contact@feel-at-home.fr (pas d'envoi serveur) |
| 1947–2030 | (auto) | Carrousel presse défilant et glissable au doigt (mobile uniquement) |

---

## 5. Fichiers externes utilisés

À fournir dans le même dossier que la page :

- **Images / vidéo du contenu** : `assets/Logo_horizontal_Feel_at_Home.svg`, `assets/hero-video-particuliers.mp4`, `assets/elisa-portait%202.jpeg` (nom avec faute et espace), `assets/press-leroch.jpg`, `assets/press-ici.jpg`, `assets/press-grandreims.jpg`, `assets/press-youtube.jpg`, `images/carte-zones.jpg`
- **Décors appelés par le CSS** : `assets/feuille-{haut,bas,droite}-{bleu,beige}.svg`, `assets/balai-bleu.svg`, `assets/pchit.svg`, `assets/bg-feuillage.png`, `assets/nav-barre.svg`, `assets/fah-logo-icon.png`
- **Pages liées** : `index.html` (Pro), `faq.html`, `nos-engagements.html`, `mentions-legales.html`
- **CDN** : Google Fonts, Lucide 0.396.0 (jsDelivr)

---

## 6. « Je veux changer X » : toutes les lignes à modifier

Plusieurs informations sont répétées. Il faut toutes les changer, sinon la page (ou Google) affichera des valeurs différentes.

| Information | Lignes |
|---|---|
| Prix **Feel at Home** 18,45 € (après crédit) | 6, 14 (méta), 43–46 (JSON-LD), 1453, 1504–1505 (exemple crédit d'impôt) |
| Prix avant crédit 36,90 € | 1454, 1503 |
| Prix **Feel boost** 21,45 € / 42,90 € | 51–54 (JSON-LD), 1470, 1471 |
| Minimum d'heures | 43 & 51 (JSON-LD), 1455, 1472 |
| Téléphone / WhatsApp `07 56 83 71 74` | 32, 1289, 1768, 1772, 1822, 1837 |
| Email `contact@feel-at-home.fr` | 33, 1767, 1773, 1822, 1942 |
| Prix Pépite 2025 | 36, 1233 + 1237 (ticker ×2), 1280, 1323, 1339 |
| Messages du ticker | 1229–1232 **et** 1233–1236 (copie identique) |
| Liens du menu | 1241–1246 **et** 1259–1266 (menu mobile) |
| Frais par zone (7,30 / 9,70 / 13,80) | 1577, 1585, 1593, 1601 **et** légende 1614–1617 |
| Jours d'intervention | 1460, 1477 (« lundi au samedi ») et 1769 (« Mardi – Samedi », il s'agit des horaires de contact) |
| Note et nombre d'avis Google | 1633 |
| Ajouter / modifier un avis | Dans le 1er lot (1640–1694) **et** sa copie (1695–1750) |
| Bascule Pro/Particulier | 1249–1250 (nav), 1850–1851 (flottant, libellé « Perso ») |
| Titre et description Google | 6–7, 13–14 |

---

## 7. Points à vérifier repérés pendant l'analyse

1. **Exemple du crédit d'impôt incohérent** (ligne 1503) : « Une intervention de 2 h, formule régulière : 36,90 € ». Or 36,90 € correspond à **1 heure**. Pour 2 h, c'est 73,80 € → 36,90 € payés. À corriger : soit « 1 h », soit les montants 73,80 / −36,90 / 36,90.
2. **Zones 3 et 4 au même prix** (13,80 €). À confirmer si c'est voulu (la zone 4 ajoute 1,50 €/km au-delà).
3. **Formulaire** : il ouvre seulement la messagerie du visiteur. Un TODO (ligne 1824) prévoit un envoi serveur avant la mise en ligne.
4. **Lien CGV vide** (`href="#"`, ligne 1865) et « Mentions légales » présent deux fois dans le footer.
5. **Libellé de la bascule** : « Particulier » dans la nav, « Perso » dans les boutons flottants.
6. **Nom de fichier photo** `elisa-portait 2.jpeg` : faute (« portait ») et espace. Ça fonctionne, mais c'est fragile.
7. Sections **Avantages, Au quotidien, Zone et Elisa** absentes du menu (ancres `#avantages`, `#quotidien`, `#zone`, `#elisa` disponibles si besoin).
8. Le compteur annonce « 15 avis Google » mais le carrousel en montre 11 (normal si on n'affiche qu'une sélection).
