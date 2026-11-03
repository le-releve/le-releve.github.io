# Le Relevé

Site statique (GitHub Pages) qui présente des données publiques du Québec sous forme de graphiques et de listes à consulter et à filtrer. Source des données : ministère du Travail du Québec, sur [Données Québec](https://www.donneesquebec.ca/) (licence CC-BY 4.0).

> Les fichiers de ce dépôt sont publiés par un workflow GitHub Actions (commits « Site au AAAA-MM-JJ »). Toute modification faite directement ici doit aussi être reportée dans le dépôt source, sinon elle sera écrasée à la prochaine publication.

## Structure

| Chemin | Contenu |
| --- | --- |
| `index.html` | Page d'entrée : présentation et une carte par page, regroupées par catégorie |
| `mur/` | Le mur des conflits : arrêts de travail actifs depuis 2016 |
| `en-cours/` | Les conflits en cours : arrêts sans date de fin dans le fichier le plus récent |
| `calendrier/` | Le calendrier des négociations : dates d'expiration des conventions collectives |
| `polices/` | Police Archivo auto-hébergée (licence OFL, voir `polices/OFL.txt`) |
| `.nojekyll` | Désactive Jekyll sur GitHub Pages |

Chaque page est un fichier HTML autonome : styles, scripts et données sont intégrés.

## Navigation par catégorie

Comme sur Données Québec, les pages sont regroupées par thème. La barre de navigation (`<nav class="site-nav">`, identique sur toutes les pages) affiche :

- **Le Relevé** : lien vers la page d'entrée;
- un menu déroulant par catégorie (`<details class="site-categorie">`). Il n'y a pour l'instant qu'une catégorie, **Relations de travail**, qui contient les trois pages.

Le menu fonctionne sans JavaScript. Un petit script le ferme sur un clic à l'extérieur ou sur Échap. Sur les pages d'une catégorie, l'élément `details` reçoit la classe `actif` (catégorie en gras) et le lien de la page courante porte `aria-current="page"`.

Pour ajouter une page à une catégorie, ajoutez un `<li>` dans le menu de **toutes** les pages, et une carte dans la section correspondante de `index.html`. Pour une nouvelle catégorie, dupliquez le bloc `details.site-categorie` dans la navigation, et une `section.theme` dans `index.html`.
