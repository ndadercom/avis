# avis — lien d'avis Google de Ndadercom Optique

Petite page publique, publiée avec **GitHub Pages** : https://ndadercom.github.io/avis/

## À quoi elle sert

L'application de gestion du magasin (dépôt privé `ndader-gestion`) envoie aux clients un message WhatsApp « Satisfaction et avis », puis **un 2e message avec un lien seul**. Ce lien est celui de cette page.

- WhatsApp affiche une **carte** construite à partir des balises `og:` de `index.html` : l'image `carte.jpg`, le titre et la description.
- Quand le client ouvre le lien, la page le renvoie aussitôt vers la **fenêtre d'avis Google** du magasin (lien `g.page/r/…/review`). Si le renvoi ne marche pas, un bouton fait la même chose.

Pourquoi cette page plutôt qu'un lien Google direct (05/11/2026) : le long lien de recherche Google donnait une carte vide (« www.google.com ») et s'affichait en entier chez le client ; le lien court `g.page` affiche une carte en anglais qui inquiète ; TinyURL perd la carte.

## Fichiers

- `index.html` : la page (balises de la carte, texte, bouton, renvoi automatique).
- `carte.jpg` : l'image de la carte, 1200 × 630, moins de 300 Ko (limite conseillée pour WhatsApp).
- `README.md` : ce fichier.

**Aucune donnée client ici** : ce dépôt est public.

## Changer quelque chose

- **Le lien d'avis Google** : seulement l'attribut `href` du bouton `id="avis"` dans `index.html` (le renvoi automatique le reprend).
- **Le titre ou la description de la carte** : les balises `og:title` et `og:description`.
- **L'image** : remplacer `carte.jpg` (même nom, 1200 × 630, JPEG de moins de 300 Ko). Si le nom change, changer aussi `og:image` et `og:image:secure_url`.
- Si l'adresse de la page change (autre compte ou autre nom de dépôt), changer `og:url`, `og:image`, `og:image:secure_url`, puis le réglage de l'application (Paramètres › Messages WhatsApp › Lien d'avis Google).

## Publier

1. GitHub Desktop : « Commit to main », puis « Push origin ».
2. La première fois : sur github.com, dépôt `avis` › Settings › Pages › Build and deployment › Source « Deploy from a branch », Branch `main`, dossier `/ (root)`, Save.
3. Attendre 1 à 2 minutes, puis vérifier avec un vrai envoi WhatsApp (bouton « M'envoyer un essai » de l'application) et une capture **du côté qui reçoit**. WhatsApp peut garder une ancienne carte en mémoire quelque temps.
