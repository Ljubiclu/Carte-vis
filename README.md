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

## Attribution

Fond de carte : © contributeurs OpenStreetMap (openstreetmap.org/copyright) — déjà crédité automatiquement en bas de la carte.
