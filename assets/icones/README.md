# Icônes EVOLIFT

Ce dossier contient les icônes utilisées par l'app (logo + barre de navigation).
Ce sont des exemples : remplace-les par tes propres images en gardant **exactement
le même nom de fichier**. Le code va automatiquement les afficher au prochain
rechargement de la page — rien à changer dans le HTML.

| Fichier              | Utilisé pour                              |
|----------------------|--------------------------------------------|
| `logo.svg`           | Logo EVOLIFT (en-tête + écran de connexion) |
| `nav-home.svg`       | Onglet "Accueil"                            |
| `nav-workout.svg`    | Onglet "Séances"                            |
| `nav-body.svg`       | Onglet "Corps" (Body Graph)                 |
| `nav-planning.svg`   | Onglet "Planning"                           |
| `nav-settings.svg`   | Onglet "Réglages"                           |

## Comment remplacer une icône
1. Prépare ton image (idéalement carrée, fond transparent, ~64×64 px minimum).
2. Renomme-la exactement comme le fichier à remplacer (ex : `nav-home.svg`).
3. Écrase le fichier existant dans ce dossier (sur GitHub : ouvre le fichier →
   "..." → "Delete file" puis "Add file" → "Upload files", ou utilise
   `git add` / `git commit` / `git push` en local).
4. Recharge l'app : ta nouvelle icône apparaît directement.

## Utiliser du PNG/JPG à la place du SVG
Si tu préfères des images bitmap (PNG/JPG) plutôt que du SVG :
1. Nomme le fichier pareil mais avec la bonne extension (ex : `nav-home.png`).
2. Dans `index.html`, cherche les lignes `src="assets/icones/..."` et remplace
   `.svg` par `.png` (ou `.jpg`) pour l'icône concernée.

## Sécurité intégrée
Si un fichier est manquant, corrompu, ou pas encore ajouté, l'app bascule
automatiquement sur une icône Material par défaut — l'app ne casse jamais,
même si le dossier est incomplet.
