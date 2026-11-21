# The House 🏠

Un jeu d'aventure en pixel. Une maison au bout de la route… tu entres juste pour demander ton chemin.

**Jouer :** ouvre `index.html`, ou va sur la page GitHub Pages du projet.

---

## Mettre le jeu sur GitHub (une seule fois)

1. Va sur **github.com** et connecte-toi.
2. En haut à droite, clique sur **+** puis **New repository**.
3. Nom : `the-house`. Coche **Public**. Clique sur **Create repository**.
4. Sur la page qui s'ouvre, clique sur **uploading an existing file**.
5. Ouvre le fichier zip et **glisse tout son contenu** dans la page. Il faut glisser les fichiers et les dossiers qui sont *dedans*, pas le zip lui-même.
   - ⚠️ Le dossier `.github` est caché sur certains ordinateurs. Si tu ne le vois pas, regarde l'étape « Application pour ordinateur » plus bas.
6. Clique sur **Commit changes**.

## 📱 Application pour téléphone et tablette (la plus simple)

1. Dans ton projet GitHub : **Settings** → **Pages**.
2. Dans « Branch », choisis **main** et **/ (root)**, puis **Save**.
3. Attends 1 à 2 minutes. GitHub affiche l'adresse du jeu, par exemple
   `https://TON-NOM.github.io/the-house/`
4. Ouvre cette adresse sur ton téléphone :
   - **Android (Chrome)** : menu ⋮ → **Installer l'application** (ou « Ajouter à l'écran d'accueil »).
   - **iPhone / iPad (Safari)** : bouton Partager → **Sur l'écran d'accueil**.
   - **Ordinateur (Chrome ou Edge)** : l'icône **Installer** dans la barre d'adresse.

L'icône de la maison apparaît comme une vraie app. Le jeu s'ouvre en plein écran, et il marche même **sans internet** une fois qu'il a été ouvert une première fois.

## 💻 Application pour ordinateur (Windows, Mac, Linux)

GitHub peut fabriquer un vrai fichier à installer (`.exe` pour Windows, `.dmg` pour Mac, `.AppImage` pour Linux).

1. Vérifie que le fichier `.github/workflows/build-app.yml` est bien dans ton projet. Sinon :
   **Add file** → **Create new file**, tape le nom `.github/workflows/build-app.yml`, puis colle dedans le contenu de ce fichier.
2. Va dans l'onglet **Actions** et clique sur **Fabriquer l'application** puis **Run workflow**.
3. Attends 5 à 10 minutes, jusqu'à ce que la pastille soit verte ✅.
4. Clique sur ce passage (le « run ») : en bas, dans **Artifacts**, télécharge `the-house-windows-latest` (ou mac, ou ubuntu).

**Pour avoir une page de téléchargement propre (Releases) :**
à droite de ton projet, clique sur **Create a new release**, tape le tag `v1.0.0`, puis **Publish release**.
Quelques minutes plus tard, les fichiers à télécharger apparaissent dans cette release.

> Windows ou Mac peuvent afficher « application non reconnue », parce qu'elle n'est pas signée.
> - Windows : **Informations complémentaires** → **Exécuter quand même**.
> - Mac : clic droit sur l'app → **Ouvrir**.

## Mettre à jour le jeu

Remplace `index.html` dans ton projet GitHub : **Add file** → **Upload files**, puis **Commit**.

- **Téléphone :** l'app se met à jour toute seule la prochaine fois qu'elle s'ouvre avec internet.
- **Ordinateur :** relance **Run workflow**, ou crée une nouvelle release, par exemple `v1.0.1`.

## Ce qu'il faut savoir

- Les **sauvegardes** sont gardées dans l'appareil. Une sauvegarde faite sur le téléphone n'est pas sur l'ordinateur.
- Le **mode 2 joueurs** sur le même écran marche partout, y compris avec deux manettes.
- Le **mode en ligne « L'Ombre parmi nous »** marche seulement quand le jeu est ouvert dans Claude. Dans l'app téléchargée, ce bouton affiche un message et ne lance pas de partie.

## Dossiers

| Fichier | À quoi il sert |
|---|---|
| `index.html` | Le jeu entier |
| `manifest.webmanifest`, `sw.js`, `icons/` | L'app à installer sur téléphone (et le jeu sans internet) |
| `desktop/` | L'app pour ordinateur (Electron) |
| `.github/workflows/build-app.yml` | La recette que GitHub suit pour fabriquer l'app pour ordinateur |
