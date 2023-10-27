# La recherche documentaire: outils et méthode

Vous trouverez ici, non pas tout le contenu du cours, mais quelques liens et explications

## Catalogues et bases de données

- [Catalogue de l'EnC](https://catalogue.chartes.psl.eu/): vous n'y trouverez que les ouvrages présents à la bibliothèque
- [ChartExplore](https://catalogue.explore.psl.eu/primo-explore/search?vid=33PSL-ENC_V1) : outil de recherche de l'ÉnC. Interroge également les bases de données. Pour accéder à plus de références, choisir `Élargir aux documents sans texte intégral`
- [Sudoc](https://www.sudoc.abes.fr/): regroupe les catalogues de toutes les bibliothèques universitaires de France
- [BnF](https://catalogue.bnf.fr/index.do): le catalogue de la Bibliothèque nationale de France

- [Persée](https://www.persee.fr/): Accès ouvert à des collections complètes de publication en SHS et en science. 
- [Cairn](https://www.cairn.info/): Ouvrages en ligne, dont les encyclopédies de poche des collections *Repères* et *Que sais-je* -- y accéder via ChartExplore pour pouvoir consulter les titres.
- [JSTOR](https://www.jstor.org/): Articles de revue universitaires, essentiellement en anglais -- y accéder via ChartExplore pour pouvoir consulter les titres.


- RI OPAC: une base bibliographique pour le Moyen Âge




## Zotéro

- Zotéro est un *outil de gestion bibliographique*: il permet:
1. de collecter les sources biblio, de les organiser, 
2. de gérer la mise en forme des références dans les traitements de texte


- Insérer des citations dans LibreOffice: cliquer sur l'icône `Add/Edit Citation`. 
- Imprimer la bibliographie: icône Add/Edit Bibliography
- Importer une bibliographie depuis Zotero: dans Zotero, clic droit (par exemple sur la collection ou la sous-collection, ou sur un ensemble de références selectionnées) -- créer une bibliographie -- copier dans le presse papier. Une fois de retour dans LibreOffice, coller le contneu du presse-papier (Clt V ou Edit -- Past). Avec cette méthode, le lien avec les références dans Zotero est défait: pas d'actualisation possible

- **nb** Si les icônes Zotero n'apparaissent pas, aller dans View -- Toolbar : cocher zotero

Pour trouver de l'aide/des astuces: 
- [Documentation Zotero Fr](https://docs.zotero-fr.org/adding_items_to_zotero/)
- [Forum Zotero](https://forums.zotero.org/)
- [La Boîte à outils des historien.ne.s](https://boiteaoutils.info/2011/12/petites-astuces-zotero-mise-en-forme/)

Pour télécharger des styles Zotero:
- [Zotero Style Repository](https://www.zotero.org/styles)

Outil pour modifier un style CSS:
- [Editor citation styles](https://editor.citationstyles.org/about/)

Tutoriels pour modifier un style:
- [tutoriel de thomas lienhard](http://www.thomaslienhard.fr/TutorielZotero.html)
- [tutoriel du blog Zotero](https://zotero.hypotheses.org/758)

Vérifier si le nouveau style csl est valide:
- [CSL style validator](https://validator.citationstyles.org/)

Exemple: mettre le prénom de l'auteur entre parenthèses dans la bibliographique, en partant du style "ENS de Lyon - Centre d'ingénierie documentaire"
1.  Enregistrer le style sous un nouveau nom (en conservant bien l'extension ".csl")
1. Ajouter dans ce nouveau style, dans la macro ` <macro name="author-bib">`, la ligne suivante: ` <name-part name="given" prefix='(' suffix=')' />`. Attention à bien placer cette ligne, par exemple sous la ligne équivalente pour le nom de famille (`<name-part name="family" font-variant="small-caps"/>`)
1. Charger ce nouveau style dans Zotero (dans: Edition - Préférences - Citer, cliquer sur le + et selectionner le chemin de votre nouveau style)

Explication: on donne des indications pour une partie du nom de l'auteur (`name-part`); il s'agit du prénom (`name="given"`); on encadre le prénom par un préfixe et un suffixe, respectivement une parenthèse ouvrante et une parenthèse fermante.

## Rédiger avec LibreOffice




### Utiliser les niveaux de titre et le mode plan

- Dans l'option de formatage, utiliser les différents niveaux de titre (`heading`) pour attributer des niveaux à vos titre (section, sous-section, etc)
- Pour numéroter un niveau de titre, par exemple `heading 1`: choisir Outils - numérotation des chapitres 
- Utiliser le mode plan ("Navigateur"): `Vue - navigateur`, ou `Fn 5`. Utiliser les flèches droite-gauche pour modifier le niveau d'un titre (par exemple passer de `heading 3` à `heading 2`, et es flèches haut-bas pour déplacer la section et ses dépendances (texte, sous-partie) ailleurs dans le document.
- Insérer une table des matières:  `Insertion - table des matières`. Penser à modifier le titre pour qu'il apparaisse en français.
- Pour mettre à jour la table des matières (ou toute autre table): sur la table, faire un clic droit - sélectionner `mettre à jour l'index`
- Si l'on insère une image (`Insertion - image`), un clic droit permet d'insérer une légende, dont le contenu apparaîtra ensuite dans la table des figures. Pour imprimer celle-ci: même méthode que pour la table des matières, mais sélectionner `table of figures`


### Faire une feuille de style

-  Faire apparaitre le panel des styles: `Affichage - Styles` (ou: `Fn 11`)
- **nb** Il faut différencier les styles pour les caractères et les styles pour les paragraphes.
- Exemple de style préexistant: les styles de titre (déjà vus), le style pour les citations, le style de corps de texte (`body`), celui des notes de bas de page (`footnote`) 
- Pour modifier un style déjà existant: clic droit sur le style - `Modifier`. Ou: flèche à droite, `Modifier le style`
- Pour créer un nouveau style: clic droit - ` nouveau` . Ou: flèche à droite, `Nouveau style à partir de la sélection`

<!--3. Footer
- FN11 pour faire apparaître les styles (ou bien ds style-gérer les styles): syle pour paragrpahe - caractère- contours des images - pages - liste. Exemple pour defautpagesytle:
- ajouter un footer, puis insertion: numéro de page; RQ: on peut aussi ajouter header

Page de titre
- Insertion -autre saut - saut manuel - selectionner un style - numéro de page: pour que numéotation commence à cette page
- la première page: firststyle -> pas de footer
-->

- **Enregistrer sa feuille de style pour la réutiliser**: `fichier -modèle: enregistrer comme modèle - choisir une catégorie (my templates) - set as defaut template`. Si vous modifiez votre style par la suite en cours de rédaction, refaite l'opération.
- Vous pouvez aussi aller dans `Styles - charger des styles depuis un modèle`


**Pour aller plus loin**

- Un tutoriel très clair: [tutorielrennes2](https://tutos.bu.univ-rennes2.fr/c.php?g=675808&p=4904731)
- le guide officiel: [guide](https://wiki.documentfoundation.org/images/7/70/GS5103FR-Styles_et_mod%C3%A8les.pdf)

### Travailler avec un document maître

- Utile  pour gérer des documents volumineux (par exemple des mémoires)
- Le document maître appelle plusieurs sous-documents (par exemple les différentes sections), qu'il prend en compte pour la numérotation des pages, l'impression de la table des matières, etc
- Cette insertion se fait au moyen de liens
- Les styles créés dans les sous-documents sont automatiquement importés dans le document maître; mais s'il y a des styles du même nom dans le document maître et le sous-document, la priorité est  donnée au style du document maître, ce qui permet d'avoir des styles homogènes dans l'ensemble du document final.
- Les modifications du document maître ne se répercutent pas dans les sous-documents

- Pour  créer un document maître: `fichier - nouveau-document maitre`. L'extension de ce document est  `odm`
- Pour rattacher un sous-document au document maître: dans le navigateur, sélectionner là où doit être inséré le sous-document (au début, il y a simplement: "text"), cliquer  sur `insérer` et choisir  `File` (pour utiliser un document déjà existant) ou  `new document`
- On peut  voir alors les  sous-documents et les textes rédigés dans le document-maître
- Dans le navigateur, `update` permet de mettre à jour ce que l'on voir lorsque l'on a modifié un sous-document
- On peut ainsi travailler chaqye partie ou sous-partie dans un document différent, et tout regrouper dans le document maître, dans lequel on fera apparaître par exemple la table des matières


### Enregistrement automatique et versions

- `Outils - options - Load/save - General`: choisir `save autorecovery` : sauvegarde automatique toutes les 10 minutes (on peut changer la durée). **nb** il faut le faire pour chaque document de travail.
- Enregistrer des versions: `Fichiers- Versions`: cocher `always save a new version on closing`: cela permet d'enregistrer un historique de l'état du document
- à chaque étape important de la rédaction: enregistrer manuellement une version en y mettant un commentaire. Il est possible ensuite, en cliquant sur la version et en choisissant `open`, d'ouvrir un état antérieu du document.
