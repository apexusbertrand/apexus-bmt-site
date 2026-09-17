# Apexus-BMT — Site vitrine

Site vitrine à page unique pour Apexus-BMT (Bertrand Marat), conseil en
transformation des processus métiers et en architecture des systèmes
d'information. Publié sur **apexus.fr** via GitHub Pages.

## Contenu

- `index.html` — la page complète (HTML/CSS/JS), autonome : aucune
  dépendance externe hors Google Fonts (police *Inter*) et le widget de
  chat `@n8n/chat` (chargé depuis un CDN). Logo, photo et icônes sont
  intégrés directement dans le fichier.
- `CNAME` — déclare le domaine personnalisé `apexus.fr` à GitHub Pages.

## Chat en ligne

Le bouton de chat en bas de page est branché sur un workflow n8n
(*Chat Trigger* → agent IA Claude) qui connaît les services, l'approche et
les coordonnées d'Apexus-BMT. L'URL du webhook n8n est définie dans le
`<script type="module">` en fin de fichier `index.html`.

## Ouvrir en local

Il suffit d'ouvrir `index.html` dans un navigateur, aucun serveur requis
(le chat nécessite une connexion internet pour charger le widget).

## Hébergement — GitHub Pages

1. Dans les paramètres de ce dépôt : **Settings → Pages**.
2. Sous « Build and deployment », choisir **Deploy from a branch**.
3. Sélectionner la branche `main` et le dossier `/ (root)`, puis **Save**.
4. Le fichier `CNAME` fait apparaître automatiquement `apexus.fr` comme
   domaine personnalisé dans ces mêmes paramètres.
5. Chez le registrar du domaine (OVH), pointer les DNS vers GitHub Pages :
   - Domaine racine `apexus.fr` : 4 enregistrements **A** vers
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
     `185.199.111.153`.
   - `www.apexus.fr` : un enregistrement **CNAME** vers
     `apexusbertrand.github.io.`
6. Une fois les DNS propagés, cocher **Enforce HTTPS** dans Settings → Pages.

## Mise à jour du contenu

Le fichier est un simple export statique : toute modification de contenu
implique de régénérer et remplacer `index.html`.
