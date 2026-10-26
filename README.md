# Courbe de poids

Application web progressive (PWA) de suivi du poids : pesées, objectifs, graphique, notes.
Version web de l'application Python/Toga d'origine. Elle fonctionne hors ligne et s'installe sur l'écran d'accueil d'un téléphone.

Adresse : https://sebsebd.github.io/Courbe.de.poids/

## Fichiers

- `index.html` : toute l'application (interface, logique, graphique)
- `manifest.webmanifest` : nom, icônes et couleurs pour l'installation
- `sw.js` : service worker (fonctionnement hors ligne)
- `icons/` : icônes de l'application
- `.nojekyll` : indique à GitHub Pages de servir les fichiers tels quels

## Mise en ligne avec GitHub Pages

1. Déposer ces fichiers à la racine du dépôt `Courbe.de.poids` (branche `main`).
2. Sur GitHub : Settings > Pages > Source : « Deploy from a branch », branche `main`, dossier `/ (root)`.
3. Après une ou deux minutes, l'application est disponible à l'adresse ci-dessus.

## Installer sur le téléphone

- iPhone (Safari) : bouton Partager > « Sur l'écran d'accueil ».
- Android (Chrome) : menu ⋮ > « Installer l'application ».

## Données

Les pesées, objectifs et notes sont enregistrés dans le navigateur de l'appareil (aucun serveur).
Le menu Infos / Mémo permet d'exporter une sauvegarde et d'importer un fichier, y compris
les anciens `pesees.json` et `objectifs.json` de la version Python.

Ne pas déposer ses fichiers de données personnelles dans le dépôt : il est public.

## Mettre à jour l'application

Après modification des fichiers, changer `VERSION` dans `sw.js` (par exemple `cdp-v2`)
pour que les téléphones téléchargent la nouvelle version.
