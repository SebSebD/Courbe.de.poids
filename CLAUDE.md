# Courbe de poids – consignes de travail

Appli PWA en un seul fichier (`index.html`) + `sw.js` + `manifest.webmanifest`.

## Avant de dire qu'un changement est terminé
1. Extraire le dernier `<script>` d'index.html et le passer à `node --check`.
2. Changement visuel : prendre une capture avec Chrome headless
   (`"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --screenshot=<fichier> --window-size=390,844 file://<chemin>/index.html`)
   dans l'état normal et dans l'état modifié, et la regarder. Sinon, dire que ce n'est pas vérifié.
   Lancer avec `</dev/null >/dev/null 2>&1 &` puis `sleep 20` (pas de `timeout` sur macOS ; ne jamais laisser une commande lire stdin). Avec `--headless=new` la capture sort à 2× et un peu rognée sur la droite : s'en servir pour les positions verticales/couleurs, pas pour juger le centrage exact.
3. Règles CSS d'un état particulier (ex. mode démo) : les scoper (`html.demo …`) et vérifier qu'elles n'écrasent pas l'état par défaut.
4. Relire la demande point par point (positions, tailles, durées, textes, couleurs).
5. Bumper `VERSION` dans `sw.js`.
6. Ne commit/push que sur demande (`main` suit `origin/main`).

## Pièges
- macOS : `sed -i` demande `''` ; préférer python pour éditer.
- Toutes les données passent par `KEYS` (localStorage) ; le mode démo les redirige vers `cdp.demo.*`. Toute nouvelle clé de stockage doit passer par `KEYS` et `DEMO_KEYS`.
