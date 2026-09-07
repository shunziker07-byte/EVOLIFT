# EVOLIFT

Application de musculation — séances, planning, body graph & récupération — dans une interface **Obsidian Luxe** (glassmorphism, accents fuchsia et sable-or).

100% front-end, sans backend : HTML + Tailwind CSS (CDN) + JavaScript vanilla. Les comptes créés dans l'app sont conservés en mémoire pendant la session (pas de `localStorage` — voir *Limites* ci-dessous).

## ✨ Fonctionnalités

- **Connexion / Inscription** — e-mail + mot de passe, et un flux "Google" simulé (voir *Limites*).
- **Accueil** — Daily Score, volume/calories/récupération du jour, séance prioritaire, statistiques du mois, état musculaire, conseil du Coach IA.
- **Séances** — entraînement en direct : chrono, minuteur de repos, validation de série (charge/répétitions), ajout d'exercice, écran de fin avec volume total.
- **Corps (Body Graph)** — cartographie de charge musculaire (Vue Face / Dos / Volume hebdo), répartition du volume par groupe musculaire, évaluation IA de symétrie, test de fatigue du jour.
- **Planning** — split hebdomadaire (cycle Push/Pull/Legs), sélection de jour, réorganisation des exercices, déplacement de séance, export `.ics`.
- **Réglages** — préférences d'entraînement (incrément de charge, repos auto, RPE/RIR, mode hors-ligne), unités kg/lbs, appareils connectés, export `.json`, déconnexion, réinitialisation des statistiques.
- **Icônes personnalisables** — logo et icônes de navigation chargés depuis `assets/icones/`, avec repli automatique sur les icônes Material par défaut si un fichier est manquant.

## 📁 Structure du projet

```
evolift/
├── index.html                  # Page unique de l'application (SPA)
├── assets/
│   ├── css/
│   │   └── style.css           # Styles custom (au-delà des utilitaires Tailwind)
│   ├── js/
│   │   ├── tailwind.config.js  # Design tokens (couleurs, typographie, espacements)
│   │   └── app.js              # Logique de l'application (état, rendu, auth, timers)
│   └── icones/                 # Logo + icônes de navigation (remplaçables librement)
│       ├── logo.svg
│       ├── nav-home.svg
│       ├── nav-workout.svg
│       ├── nav-body.svg
│       ├── nav-planning.svg
│       ├── nav-settings.svg
│       └── README.md           # Comment remplacer les icônes
├── README.md
├── LICENSE
└── .gitignore
```

## 🚀 Lancer le projet

Aucune installation ni build requis.

**Option 1 — ouvrir directement**
Double-clique sur `index.html` (ou ouvre-le depuis ton navigateur).

**Option 2 — petit serveur local** *(recommandé, notamment pour que les icônes se chargent sans restriction de sécurité navigateur)*
```bash
cd evolift
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```
ou avec Node :
```bash
npx serve .
```

## 🌐 Déployer sur GitHub Pages

1. Pousse ce dossier sur un dépôt GitHub.
2. Dans **Settings → Pages**, choisis la branche `main` et le dossier `/ (root)`.
3. Ton app sera disponible à `https://<ton-user>.github.io/<ton-repo>/`.

## 🎨 Remplacer les icônes

Voir [`assets/icones/README.md`](./assets/icones/README.md) : dépose tes propres images dans ce dossier en gardant les mêmes noms de fichiers, l'app les affichera automatiquement au rechargement.

## ⚠️ Limites à connaître (prototype front-end)

- **Pas de vrai backend.** Comptes et données ne sont conservés qu'en mémoire pendant la session (onglet ouvert) — rien n'est envoyé à un serveur, et un rechargement de page réinitialise la session.
- **Mots de passe non sécurisés.** Le hash utilisé est une fonction simple à but de démo, pas un algorithme cryptographique (type bcrypt/argon2). Ne pas utiliser de vrais mots de passe sensibles.
- **"Connexion Google" simulée.** Il n'y a pas de vraie intégration OAuth Google — le bouton ouvre un petit formulaire qui simule la connexion.

### Pour aller plus loin (production)
Pour une vraie authentification et une persistance des données (multi-appareils), il faudra remplacer la couche d'état de `assets/js/app.js` par des appels vers un vrai backend (Firebase, Supabase, ou une API maison).

## 🎨 Design system

Le fichier `assets/js/tailwind.config.js` contient tous les tokens (couleurs, typographie `Hanken Grotesk`, espacements) du design system **Obsidian Luxe**, partagé avec LISTMAX et CREAFOOD.

## 📄 Licence

MIT — voir [LICENSE](./LICENSE).
