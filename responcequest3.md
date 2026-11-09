# Exercice : repérer les problèmes on-page

## Code analysé

```html
<head>
  <title>Accueil</title>
</head>
<body>
  <h2>Bienvenue sur notre site</h2>
  <h1>Nos produits</h1>
  <a href="/produit?id=42">cliquez ici</a>
  <a href="/produit?id=43">cliquez ici</a>
</body>
```

## Problèmes identifiés

| # | Problème | Pourquoi c'est un problème | Correction |
|---|----------|----------------------------|------------|
| 1 | **`<title>` trop générique** ("Accueil") | Aucun mot-clé, pas de marque, seulement 7 caractères au lieu de ~50-60. Il n'apporte rien à Google ni à l'utilisateur dans les résultats de recherche. | `<title>Vélos électriques et trottinettes en ville \| CycloShop</title>` |
| 2 | **Pas de meta description** | Google génère un extrait au hasard, ce qui réduit le taux de clic (CTR). | Ajouter une description de ~150-160 caractères, orientée bénéfice. |
| 3 | **Hiérarchie des titres incorrecte** : le `<h2>` est placé avant le `<h1>` | La structure doit partir du `<h1>` puis descendre en `<h2>`, `<h3>`. Cette inversion gêne les crawlers et les lecteurs d'écran (accessibilité). | Mettre le `<h1>` en premier, puis les `<h2>`. |
| 4 | **`<h1>` vague** ("Nos produits") | Il doit résumer le sujet principal de la page avec le mot-clé visé. Ici, aucun mot-clé. | `<h1>Vélos électriques, trottinettes et accessoires</h1>` |
| 5 | **URLs non propres** (`/produit?id=42`) | Query string illisible, sans mot-clé, qui ne dit rien sur le contenu de la page. | `/produits/velo-electrique-pliable` |
| 6 | **Ancres non descriptives** ("cliquez ici") | Elles n'indiquent ni à l'utilisateur ni à Google où mène le lien. Le maillage interne perd sa valeur sémantique. | Utiliser le nom du produit comme ancre. |
| 7 | **Deux liens avec la même ancre** vers deux pages différentes | Google ne peut pas distinguer les deux destinations. C'est aussi une mauvaise pratique d'accessibilité. | Une ancre unique et descriptive par lien. |

## Version corrigée

```html
<!doctype html>
<html lang="fr">
<head>
  <title>Vélos électriques et trottinettes en ville | CycloShop</title>
  <meta name="description" content="Découvrez notre sélection de vélos électriques, trottinettes et accessoires pour rouler en ville toute l'année. Livraison offerte." />
</head>
<body>
  <h1>Vélos électriques, trottinettes et accessoires</h1>
  <h2>Nos produits</h2>
  <ul>
    <li><a href="/produits/velo-electrique-pliable">Vélo électrique pliable</a></li>
    <li><a href="/produits/trottinette-tout-terrain">Trottinette tout-terrain</a></li>
  </ul>
</body>
</html>
```

## À retenir

- **Title et meta description** : uniques par page, avec le mot-clé en premier.
- **URLs** : lisibles, en minuscules, avec des tirets, sans paramètres.
- **Titres** : un seul `<h1>`, puis `<h2>`/`<h3>` sans sauter de niveau.
- **Maillage interne** : des liens avec des ancres descriptives.