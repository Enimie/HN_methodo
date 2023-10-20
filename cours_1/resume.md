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


