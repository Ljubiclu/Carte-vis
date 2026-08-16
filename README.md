# Carte de bord — Vis

Un site d'une seule page : carte interactive de l'île de Vis (Croatie) avec restaurants, plages et points de vue, tes recommandations, et un vrai fond de carte OpenStreetMap (les rues apparaissent en zoomant).

## Contenu du pack

- `index.html` — le site complet (HTML + CSS + JS dans un seul fichier)
- `favicon.svg` — l'icône d'onglet (boussole)
- `README.md` — ce fichier

Aucune installation, aucun serveur, aucune base de données nécessaire : c'est un site 100% statique. Il charge juste deux ressources externes au démarrage (les polices Google Fonts et la bibliothèque Leaflet.js + les tuiles OpenStreetMap), donc il faut une connexion internet pour l'utiliser, mais rien à compiler.

## Mettre le site en ligne (gratuit, 5 minutes)

### Option la plus simple — Netlify Drop
1. Va sur https://app.netlify.com/drop
2. Glisse-dépose le dossier entier (`index.html` + `favicon.svg`) dans la page
3. Netlify te donne une URL publique immédiatement (ex: `random-name-123.netlify.app`)
4. Tu peux ensuite créer un compte gratuit pour renommer l'URL ou brancher ton propre nom de domaine

### Option GitHub Pages
1. Crée un nouveau dépôt GitHub (public)
2. Mets `index.html` et `favicon.svg` à la racine du dépôt
3. Dans les Paramètres du dépôt → Pages, choisis la branche `main` et le dossier `/ (root)`
4. Ton site sera visible à `https://<ton-nom>.github.io/<nom-du-depot>/`

### Option Vercel
1. Va sur https://vercel.com/new
2. Importe le dossier ou glisse-dépose les fichiers
3. Déploiement automatique, URL fournie immédiatement

### Nom de domaine personnalisé
Les trois options ci-dessus permettent de brancher un nom de domaine que tu achètes (Namecheap, OVH, Google Domains, etc.) via leurs réglages "Domains" / "Custom domain" — il suffit généralement d'ajouter un enregistrement DNS de type CNAME.

## Modifier le contenu

Tout le contenu (lieux, adresses, descriptions, recommandations) est dans le tableau `PLACES` en haut du `<script>` dans `index.html`. Chaque lieu suit ce format :

```js
{cat:"resto", name:"Nom du lieu", lat:43.0594, lng:16.1561,
 place_id:"...", price:"€€€€", zone:"Quartier",
 desc:"Description...", rec:"Ta recommandation...", hero:true}
```

- `cat` : `"resto"`, `"plage"` ou `"vue"`
- `hero:true` (optionnel) : ajoute une étoile ★ "coup de cœur"
- `place_id` : identifiant Google Maps, utilisé pour le bouton "Voir sur Google Maps" (à trouver en cherchant le lieu sur Google Maps → Partager → Intégrer une carte, ou via l'URL du lieu)

Après modification, il suffit de re-déposer le fichier mis à jour sur Netlify/Vercel/GitHub pour publier les changements.

## Ajouter tes propres photos

Le site affiche une **galerie glissable** (plusieurs photos possibles par lieu) — il suffit de déposer les fichiers, aucune modification de code nécessaire.

1. Crée un dossier `images/` à côté de `index.html` (déjà présent dans ce pack, avec les photos de Peškarija 1911 et Lola Bar déjà ajoutées)
2. Nomme tes fichiers `<nom-du-lieu>-1.jpg`, `<nom-du-lieu>-2.jpg`, etc. (jusqu'à 6 photos par lieu), en suivant les noms ci-dessous
3. Redépose le dossier complet (`index.html` + `favicon.svg` + `images/`) sur Netlify

Tant qu'aucun fichier n'existe pour un lieu, l'illustration stylisée reste affichée automatiquement — aucun risque d'image cassée.

### Restaurants
- Peškarija 1911 → `images/peskarija-1911-1.jpg`, `-2.jpg`... ✅ déjà ajoutées
- Lola Bar → `images/lola-bar-1.jpg`, `-2.jpg`... ✅ déjà ajoutées
- Pojoda → `images/pojoda-1.jpg`
- Fort George → `images/fort-george-1.jpg`
- Buffet Vis → `images/buffet-vis-1.jpg`
- Villa Kaliopa → `images/villa-kaliopa-1.jpg`
- Konoba Roki's Fire → `images/konoba-roki-s-fire-1.jpg`
- Konoba Bako → `images/konoba-bako-1.jpg`
- Frutarija → `images/frutarija-1.jpg`
- Lambik → `images/lambik-1.jpg`
- Fabrika Pizza Komiža → `images/fabrika-pizza-komiza-1.jpg`
- Konoba Jastožera → `images/konoba-jastozera-1.jpg`
- Konoba Šenko → `images/konoba-senko-1.jpg`
- Stončica → `images/stoncica-1.jpg`
- Konoba Magić → `images/konoba-magic-1.jpg`
- Val 2.0 → `images/val-2-0-1.jpg`
- Konoba Vatrica → `images/konoba-vatrica-1.jpg`
- Karijola Pizza → `images/karijola-pizza-1.jpg`

### Plages
- Stiniva → `images/stiniva-1.jpg` (photo Wikimedia utilisée par défaut si absente)
- Srebrna → `images/srebrna-1.jpg`
- Prirovo → `images/prirovo-1.jpg`
- Grandovac → `images/grandovac-1.jpg`
- Gusarica → `images/gusarica-1.jpg`
- Zaglav → `images/zaglav-1.jpg`
- Milna → `images/milna-1.jpg`
- Perna → `images/perna-1.jpg`

### Vues & patrimoine
- Grotte Bleue (Bišević) → `images/grotte-bleue-bisevic-1.jpg` (photo Wikimedia utilisée par défaut si absente)
- Fort George — belvédère → `images/fort-george-belvedere-1.jpg`
- Panorama de Kut → `images/panorama-de-kut-1.jpg`
- Mont Hum → `images/mont-hum-1.jpg`
- Grotte de Tito → `images/grotte-de-tito-1.jpg`
- Vis ville — vieille ville → `images/vis-ville-vieille-ville-1.jpg`

Astuce : sur Google Maps ou Instagram, ouvre la fiche du lieu → appuie longuement sur une photo → "Enregistrer l'image", puis renomme le fichier téléchargé selon la liste ci-dessus.

⚠️ Comme ce site n'est gardé que pour ton usage personnel, c'est ok d'y mettre des photos trouvées sur Google Maps/Instagram ; si tu comptes un jour le rendre public, pense à vérifier que tu as le droit de les republier (ou remplace-les par tes propres photos).

## Attribution

Fond de carte : © contributeurs OpenStreetMap (openstreetmap.org/copyright) — déjà crédité automatiquement en bas de la carte.
