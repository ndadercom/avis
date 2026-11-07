# avis — lien d'avis Google de Ndadercom Optique

Petite page publique, publiée avec **GitHub Pages** : https://ndadercom.github.io/avis/

## À quoi elle sert

L'application de gestion du magasin (dépôt privé `ndader-gestion`) envoie aux clients un message WhatsApp « Satisfaction et avis », puis **un 2e message avec un lien seul**. Ce lien est celui de cette page.

- WhatsApp affiche une **carte** construite à partir des balises `og:` de `index.html` : l'image `carte-avis.jpg`, le titre et la description.
- Quand le client ouvre le lien, la page le renvoie aussitôt vers la **fenêtre d'avis Google** du magasin (lien `g.page/r/…/review`). Si le renvoi ne marche pas, un bouton fait la même chose.

Pourquoi cette page plutôt qu'un lien Google direct (05/11/2026) : le long lien de recherche Google donnait une carte vide (« www.google.com ») et s'affichait en entier chez le client ; le lien court `g.page` affiche une carte en anglais qui inquiète ; TinyURL perd la carte.

## Fichiers

- `index.html` : la page (balises de la carte, texte, bouton, renvoi automatique).
- `carte-avis.jpg` : l'image de la carte WhatsApp, **carrée** (800 × 800), moins de 300 Ko (limite conseillée pour WhatsApp), **texte loin des bords**. Carrée parce que WhatsApp l'affiche en petit carré à côté du titre : l'image large du début (`carte.jpg`) y était coupée ; et WhatsApp coupe encore un peu les bords du carré (essais du 05/11/2026).
- `carte-carree.jpg` : 1re image carrée, dont les bords étaient coupés. Plus utilisée, gardée pour l'historique.
- `carte.jpg` : l'image large (1200 × 630), affichée en haut de la page pendant le renvoi vers Google.
- `README.md` : ce fichier.

**Aucune donnée client ici** : ce dépôt est public.

## Changer quelque chose

- **Le lien d'avis Google** : seulement l'attribut `href` du bouton `id="avis"` dans `index.html` (le renvoi automatique le reprend).
- **Le titre ou la description de la carte** : les balises `og:title` et `og:description`.
- **L'image de la carte** : remplacer `carte-avis.jpg` (carrée, texte au centre, JPEG de moins de 300 Ko). WhatsApp garde parfois l'ancienne image en mémoire : le plus sûr est de donner un **nouveau nom** au fichier et de changer `og:image`, `og:image:secure_url`, `og:image:width` et `og:image:height`.
- Si l'adresse de la page change (autre compte ou autre nom de dépôt), changer `og:url`, `og:image`, `og:image:secure_url`, puis le réglage de l'application (Paramètres › Messages WhatsApp › Lien d'avis Google).

## Publier

1. GitHub Desktop : « Commit to main », puis « Push origin ».
2. La première fois : sur github.com, dépôt `avis` › Settings › Pages › Build and deployment › Source « Deploy from a branch », Branch `main`, dossier `/ (root)`, Save.
3. Attendre 1 à 2 minutes, puis vérifier avec un vrai envoi WhatsApp (bouton « M'envoyer un essai » de l'application) et une capture **du côté qui reçoit**. WhatsApp peut garder une ancienne carte en mémoire quelque temps.

## Si la page ne se met pas à jour

GitHub Pages met normalement 1 à 2 minutes. Il arrive que la mise en ligne échoue (étape « Deploy to GitHub Pages ») ou reste bloquée « Queued » (05/11/2026 : bloquée deux jours). Dans ce cas :

1. onglet **Actions** du dépôt, ouvrir le run bloqué, **Cancel workflow** ;
2. faire un nouvel envoi (n'importe quel petit changement, par exemple dans ce fichier) : un nouveau run démarre.

Vérifier ensuite que la page en ligne a la bonne `og:image`.
