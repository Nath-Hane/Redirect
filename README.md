# Redirect

Aiguilleur statique minimaliste hébergé sur GitHub Pages pour rediriger un QR code imprimé vers une URL modifiable à volonté.

## Changer l'URL cible

Dans [`index.html`](index.html), remplacer l'URL actuelle aux 4 emplacements :
1. `<link rel="canonical" href="...">`
2. `<meta http-equiv="refresh" content="0; url=...">`
3. `window.location.replace("...")`
4. `<a href="...">` (lien de secours)

Commit et push sur `main`.

## Déploiement GitHub Pages

1. Créer un dépôt GitHub (ex. `Redirect`) et pousser la branche `main`.
2. Aller dans **Settings → Pages → Build and deployment**.
3. Sélectionner **Deploy from a branch**, branche `main`, dossier `/ (root)`.

## Notes techniques

- **URL du QR code :** inclure le slash final (`https://nath-hane.github.io/Redirect/`). Sans le slash final, GitHub Pages ajoute une redirection `301` intermédiaire avant de servir `index.html`, ce qui ralentit l'ouverture sur mobile.
- **Délai de mise à jour :** GitHub Pages applique un cache de 10 minutes (`max-age=600`) sur les fichiers statiques.
- **Historique navigateur :** `window.location.replace()` remplace l'entrée dans l'historique afin que le bouton *Retour* sur mobile ne ramène pas sur la page de redirection.
