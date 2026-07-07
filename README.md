# L'Académie des Critiques Raffinées

Générateur trilingue (français / svenska / English) de critiques élégamment
assassines. Installable comme une PWA — fonctionne aussi hors ligne une fois
visitée une première fois.

## Fichiers

- `index.html` — l'application (interface + données intégrées)
- `manifest.json` — métadonnées PWA (nom, icônes, couleurs)
- `service-worker.js` — mise en cache pour l'usage hors ligne
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png` — icônes

Tout est statique : aucun serveur, aucune dépendance à installer.

## Déploiement sur GitHub Pages

1. Crée un nouveau dépôt sur GitHub (public), par ex. `critiques-raffinees`.
2. Pousse ce dossier tel quel, à la racine du dépôt :

   ```bash
   git init
   git add .
   git commit -m "Générateur de critiques raffinées"
   git branch -M main
   git remote add origin https://github.com/<TON-USER>/critiques-raffinees.git
   git push -u origin main
   ```

3. Sur GitHub : **Settings → Pages**
   - Source : `Deploy from a branch`
   - Branch : `main`, dossier `/ (root)`
   - Enregistre.

4. Après une minute ou deux, le site sera en ligne à :

   ```
   https://<TON-USER>.github.io/critiques-raffinees/
   ```

## Installer comme application

- **Android / Chrome desktop** : ouvre l'URL, menu ⋮ → *Installer l'application*
  (ou l'icône d'installation dans la barre d'adresse).
- **iPhone / iPad (Safari)** : ouvre l'URL, bouton Partager → *Sur l'écran d'accueil*.
- **macOS (Safari 17+)** : Fichier → *Ajouter au Dock*.

Une fois installée, l'app garde ses propres icône et fenêtre, et se relance
hors ligne grâce au service worker.

## Mettre à jour le contenu plus tard

Modifie directement les tableaux `insultData.fr`, `insultData.sv`,
`insultData.en` dans `index.html` (ou importe un nouveau fichier JSON via le
bouton *Importer* dans l'app, puis exporte pour récupérer le fichier mis à
jour). Si tu changes `index.html`, augmente aussi le numéro de version dans
`service-worker.js` (`CACHE_NAME`) pour forcer les appareils déjà installés à
récupérer la nouvelle version.

*Bona Cogitata · Bona Verba · Bona Facta · Memento Ridere*
