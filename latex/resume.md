![LaTeX](LaTeX_logo.svg.png)


[TOC]

# Premiers pas

## La structure d'un document

- un préambule
- le corps du texte entre les balises `begin{document}` et `\end{document}`

```
\documentclass[12pt,a4paper]{article} %appel de classe
%appel des packages:
\usepackage{fontspec} %package pour gérer les fontes
\usepackage{xunicode} %package pour gérer l'unicode
\usepackage{polyglossia} %package pour gérer les langues
\setmainlanguage{french}

%d'autres packages peuvent être appelés ici
%des commandes et des environnements peuvent être (re)définis ici

\begin{document}
corps du texte
\end{document}
```

- Quelques classes possibles: `article book beamer memoir`
- Quelques options possibles de l'appel de classe:
	
|option|effet|
|---   |-----  |
|`10pt`| pour une police de base en 10 pt|
|`11pt`| pour une police de base en 11 pt|
|`12pt`| pour une police de base en 12 pt|
|`onecolumn`| pour un texte sur une seule colonne (par défaut pour les classes présentées)|
|`twocolumn`| pour un texte sur deux colonnes|
|`oneside`| pour une impression en recto seulement|
|`twoside`| pour une impression en recto-verso|
|`notitlepage`| pour ne pas avoir de page de titre spécifique (par défaut pour la classe `article`)|
|`titlepage`| pour avoir une page de titre spécifique (par défaut pour la classe `book`|

## Taper en LaTeX


- le nombre d'espaces ne change rien
- un retour à la ligne  &rarr; un espace
- un tile (`~`) &rarr; espace insécable
- deux retours à la ligne ou plus &rarr; nouveau paragraphe
- `--` &rarr; demi-cadratin, `---` &rarr; cadratin
- gestion des espaces automatique avant ponctuation
- pour taper des points de suspensions: `\dots`
- tout ce qui suit le caractère `%` est ignoré (commentaire)
- attention, certains caractères sont utilisés par LaTeX: `\ ~ ^ { } % _ & $ #`. Pour insérer ces caractères dans un texte, il faut taper: `\textbackslash  \textasciitilde \textasciicircum \{ \} \% \_ \& \$ \#`


## Les packages

- *Package*:   code permettant de définir un ensemble de commandes orienté vers utilisation spécifique.  l'ensemble de ce code est contenu dans un fichier avec l'extension .sty
- Appeler un package: dans le préambule, `\usepackage{nom_du_package}`
- Obtenir la documentation: taper dans un terminal `texdoc nom_du_package`

## Les commandes

- *Commande*: bout de code qui va être interprété par le compilateur.
 - *Argument* paramètre passé à une commande et qui en modifie le comportement ou qui indique ce sur quoi elle  doit s'appliquer . 
- Syntaxe d'une commande:

1. backslash (`\` + nom de la commande)
2. entre crochets: arguments optionnels
3. entre accolades: arguments obligatoires



## Structurer un document


### Faire apparaître le titre du document

- dans le préambule: `\title{titre_du_document} \author{auteur_du_document} \date{date_du_document}` (pour qu'un de ces éléments n'apparaisse pas, laisser l'argument vide. Par défaut, si elle n'est pas indiquée, la date est celle du jour)
- dans le corps du document `maketitle`

### Commandes de section

|Commande| Sens| Numéro de niveau|
|-- |-- |-- |
|`\part{#1}`| Titre de partie| -1|
|`\chapter{#1}`| Titre de chapitre| 0|
|`\section{#1}`| Titre de section| 1|
|`\subsection{#1}`| Titre de sous-section| 2|
|`\subsubsection{#1}`| Titre de sous-sous-section| 3|
|`\paragraph{#1}`| Titre de paragraphe |4|
|`\subparagraph{#1} `| Titre de sous-paragraphe| 5|

- l'argument (`#1`) est le titre que l'on donne à la section.
- La commande `\chapter` n'existe que pour la classe `book`
- Le numéro des  niveaux de titre sert lors de l’affichage de la table des matières pour définir sa profondeur (voir dernier cours)
-  Les niveaux dont les numéros sont inférieurs à 1 provoquent un changement de page.
-  Les niveaux dont les numéros sont supérieurs à 3 ne provoquent pas de changement de paragraphe.


- Faire apparaître la table des matières: `\tableofcontents`
- Les commandes de section peuvent avoir un argument optionnel: c'est celui qui sera utilisé pour la table des matières
- Les commandes de section étoilées (par exemple `\section*{#1}`) ne sont pas numérotées et n'apparaissent pas dans la table des matières
- Pour les faire apparaître:  `\addcontentsline{toc}{#1}{#2}`. `#1` = le niveau de titre (section, chapter, etc); `#2` = le titre que l'on veut faire apparaître dans la table des matières





## Les environnements

- *environnement*:  portion de document qui a une signification spécifique et subit un traitement spécifique. L'environnement accepte le saut de paragraphe. On peut  utiliser des commandes au sein d'environnements.
- syntaxe d'un environnement:  `\begin{nom_de_l_environnement} \end{nom_de_l_environnemen}`. Tout ce qui se trouve entre ces deux balises est à l'intérieur de l'environnement
- exemple: l'environnement `abstract` de la classe `article`


# Mettre en sens, mettre en forme

## Mettre en sens

### Le paratexte

|Commande|Effet|
|-- |-- |
|`\footnote{#1}`|Note de bas de page|
|`\marginpar{#1}`|Note marginale|

- L'apparence du numéro dans la note de bas de page peut être modifiée avec `polyglossia`. Mettre  à la commande `\setmainlanguage{french}`, dans l'argument optionnel, l'option `frenchfootnote=true`


### Listes

- Au sein des environnements de liste, chaque nouvelle entrée est appelée par la commande `\item`

|Environnement|Effet|
|-- |-- |
|`itemize`|liste simple|
|`enumerate`|liste numérotée|
|`description`|liste faisant correspondre deux valeurs ensemble. La première valeur est mis dans l'argument optionnel de `\item`|

- Si l'on met un argument optionnel à `\item`, on peut modifier ponctuellement le label (l'élément précédant l'entrée dans la liste: tiret, point,...)

- Pour modifier sur l'ensemble du document le label des environnements `itemize`:  mettre  à la commande `\setmainlanguage{french}` l'option `[frenchitemlabels=true]{french}` pour obtenir un cadratin; pour choisir le label, ajouter ensuite comme option `itemlabels= ` avec le label choisi. 
- Exemple: `\setmainlanguage[frenchitemlabels=true, itemlabels=\textendash]{french}` pour obtenir un demi-cadratin.

- Pour modifier le label d'un environnement `enumerate` donné, il faut utiliser le package `enumerate`. 
Exemple: `\begin{enumerate}[label=(\Roman*)]` pour numéroter la liste en chiffres romains entre parenthèses. 
Compteurs possibles: `\alph*` (lettres de l'alphabet), `\Alph*` (lettres en majuscules), `roman*` (chiffres romains en minuscule), `\Roman*` (chiffres romains en majuscule). 
-**nb**: La commande de compteur (`\alph*`, etc) ne doit pas directement être accolée au signe =

### Les citations

|Commande ou environnement|Effet|
|-- |-- |
|`\enquote{#1}` (requiert le package `csquotes`)|Guillemets|
|`quote`|Citation sur un paragraphe|
|`quotation`|Citation sur plusieurs paragraphes|
|`\textelp{}` (requiert le package `csquotes`)|Indiquer une citation tronquée. Si l'argument est vide: met simplement des points de suspension|
|`\textins{#1}` (requiert le package `csquotes`)|Indiquer une modification de la citation|
|`\url{#1}`|Créer un lien vers une URL. Utiliser le package `hyperref` pour avoir un lien cliquable (à charger EN DERNIER) pour éviter des problèmes de compatibilité avec d'autres package|
|`verse` (requiert le package `verse`|Pour citer des vers. Voir le manuel|


## Mettre en forme: quelques commandes et environnements

### Commandes portant sur le style de caractères


|Commande|Effet|
|--- |--- |
|`\textit{#1}`|Italique|
|`\emph{#1}`|Emphase (à préférer à `textit`)|
|`\textbf{#1}`|Gras|
|`\textsc{#1}`|Petites capitales|
|`\underline{#1}`|Souligné|
|`\textsuperscript{#1}`|Exposant|
|`\textsubscript{#1}`|Indice|
|`\textcolor{#1}{#2}` (nécessite le package `xcolor`) |Mettre en couleur|


**nb** 
- `#1` est le texte à mettre en forme, sauf pour `\textcolor` où: `#1`=nom de la couleur, `#2`=texte à mettre en couleur
- La commande `\emph` n'accepte pas les sauts de ligne. Pour mettre en emphase un texte plus long, utiliser l'environnement `em`

### Commandes "à bascule" pour changer  la taille des caractères

- Si l'on veut modifier sur une portion de texte donnée la taille des caractères, il faut utiliser une commande à bascule. Le comportement de ce type de commandes est différent: elles ne prennent pas d'argument, mais sont insérées entre accolades; le texte dont la taille change est entre les accolades, après la commande.
- Exemple: {\large un texte plus gros}
- La taille obtenue est relative: elle dépend de la taille définie lors de l’appel de classe.

 Liste des commandes à bascule, pour un résultat du plus petit au plus gros (`normalsize` correspond à la taille du corps du texte, `footnotesize` à la taille des notes de bas de page):

|Commande|
|-- |
|{\tiny }|
|{\scriptsize }|
|{\footnotesize }|
|{\small }|
|{\normalsize }|
|{\large }|
|{\Large }|
|{\LARGE }|
|{\huge }|
|{\Huge }|


### Environnements modifiant l'alignement du texte

|Environnement|Effet|
|-- |--|
|`flushleft`|Justifié à gauche|
|`flushright`|Justifié à droite|
|`center`|Centré|



### Commandes modifiant ponctuellement la mise en page

|Commande|Effet|
|--|--|
|`\newline` ou `\\`|Saut de ligne; la ligne suivante n'est pas indentée|
|`\newpage` ou `\pagebreak`|Commencer une nouvelle page|
|`\noindent`|Pas d'indentation au début du paragraphe|
|`\par`|Nouveau paragraphe (à utiliser dans la définition de commandes ou d'environnements)|

**nb**: `\newpage` va mettre tout l'espace disponible restant en bas de la page; `\pagebreak` va répartir cet espace sur la page. Pour cette raison, `\newpage` vous sera plus utile.


### Encadrer du texte en le mettant dans des boites

|Commande/environnement|Effet|
|-- |--|
|`\fcolorbox{#1}{#2}{#3}` (requiert le package `xcolor`)|Mettre du texte (`#3`) dans une boite de la couleur choisie (`#1` pour le cadre, `#2` pour le fond)|
|`\fbox{#1}` (ou `\framebox{#1}`|Texte court encadré (sans changement de ligne/de paragraphe)|
|`framed`(requiert le packae `framed`)|Encadre des textes qui peuvent courir sur plusieurs lignes/paragraphes|

Il existe aussi le package `fancybox` pour créer des boites encadrées

Sur la notion de boites dans LaTeX, voir LOZANO, Vincent, [Tout ce que vous avez toujours voulu savoir sur LaTeX sans jamais oser le demander](https://archives.framabook.org/docs/latex/framabook5_latex_v1_art-libre.pdf), p. 73 *sq*.

# Gérer sa bibliographie: biblatex, biber et Zotero

## Principes

1.  un fichier au format `.bib` contient toutes les références bibliographiques ("entrées") (= fichier BibTex)
- à chaque entrée est associée une clef ("key") qui l'identifie 
- chaque entrée comporte un certain nombre d'éléments de description bibliographique (nature de la référence, titre, auteur, date, etc), chacun indiqué dans le champ correspondant.
- exemple d'entrée: 

```
@Book{maieul_rouquette_2012, 
  author = {Maïeul Rouquette and Enimie Rouquette and Brendan Chabannes},
  title = {(Xe)\LaTeX{}  appliqué aux sciences humaines},
  publisher = {Atramenta},
  date = {2012},
  address = {Tampere},
  url = {https://halshs.archives-ouvertes.fr/halshs-00924546}
}
```

Dans cet exemple, la référence est un livre (`@book`), sa clef est `maieul_rouquette_2012`, et les éléments indiqués sont les auteurs, le titre, l'éditeur, la date, le lieu de publication, et l'url pour la publication en ligne.

2. Dans le préambule, on charge le package `biblatex` et on indique le chemin du fichier `.bib` avec la commande `\addbibresource{#1}`. C'est `biblatex` qui affiche les citations selon un style choisi, en utilisant le moteur `biber`.

Exemple de préambule appelant `biblatex` et un fichier bibliographique:

```
\documentclass[a4paper]{book}
\usepackage{fontspec}
\usepackage{xunicode}
\usepackage{polyglossia}
\setmainlanguage{french}
\usepackage{biblatex}
\addbibresource{/home/user/Documents/memoire/bibliographie.bib}
```

**nb** il est possible d'appeler plusieurs fichiers bibliographiques.

3. Exemple de commandes `biblatex`:
- pour faire une citation dans le corps du texte et en note de bas de page: `\cite[#1][#2]{#3}` et `\footcite[#1][#2]{#3}`, où `#1`= une prénote (texte avant la référence), `#2`=postnote (numéro de page, texte après la référence), `#3̀`=la clef de la référence bibliographique
	- S'il n'y a qu'un seul argument optionnel, il est considéré comme l'argument `postnote`. Si l'on veut l'argument `prenote` sans `postnote`, il faut mettre l'argument `#2` vide
	- Si `#2` ne contient que le numéro de la page, le préfixe (p., pp., col.,) s'affiche automatiquement. (par défaut, on pagine en pages. Si l'on veut paginer en colonnes, il faut ajouter dans l'entrée bibliographique le champ `pagination` avec pour valeur `column` ; voir le manuel pour d'autres valeurs possibles)
	- Si la postnote contient aussi du texte, il faut faire précéder le numéro de pagination de la commande `\pno~`. 

Exemples: 

	 `\footcite[Sur ce sujet, voir][99]{maieul_rouquette_2012}`
 	 `\footcite[Sur ce sujet, voir][]{maieul_rouquette_2012}`
	 `\footcite[\pno~99 et suivantes]{maieul_rouquette_2012}`

- pour imprimer la bibliographie: `\printbibliography`

4. Trois compilations sont nécessaires: 
- compilation avec `XeLaTeX`
- compilation avec `Biber`
- nouvelle compilation avec `XeLaTeX`

- Configurer TexStudio pour compiler avec biber: `options - configurer texstudio - production - moteur de bibliographie par défaut - biber`. Il faut parfois indiquer le chemin de `biber` dans l'onglet `compilation` des configurations: on le connait en tapant `which biber` dans le terminal (pour linux)
- Pour compiler soi-même: dans un terminal, se placer là où est le fichier à compiler, et taper `xelatex nom_du_fichier`, puis `biber nom_du_fichier`.

 **nb**: 
- la première compilation produit un fichier auxiliaire `.bbl`, c'est lui que l'on compile avec Biber (mais ce n'est pas la peine de mettre l'extension si l'on compile dans le terminal)
- Si l'on compile manuellement dans le terminal, il est possible d'utiliser la commande `latexmkr`  qui fait automatiquement les compilations nécessaires. Voir sur ce sujet le blog [geekographie maïeulesque](https://geekographie.maieul.net/206)


## La base de données bibliographiques

### Types d'entrées

Quelques types d'entrées possibles; pour plus d'entrées, voir le manuel de `biblatex` p.8sq, ainsi que 
ROUQUETTE, Maïeul, [XeLaTeX appliqué aux sciences humaines](https://halshs.archives-ouvertes.fr/halshs-00924546), p.81-82 sq

|Nom|type d'entrée|
|-- |-- |
|@article| Article de revue|
|@book| Livre|
|@bookinbook|Livre dans un livre, par exemple différents écrits d'un auteur rassemblés en un seul volume|
|@collection| Ouvrage collectif mais avec des parties distinctes par auteur|
|@inbook| Partie d’un livre|
|@incollection| Partie individuelle (avec un auteur propre) dans un ouvrage collectif|
|@inproceedings| Contribution à un colloque|
|@inreference| Article de dictionnaire, d’encyclopédie, etc|
|@misc| Entrée générique, pour tout type d’entrée non catégorisable|
|@online| Ressource internet (sans équivalent physique)|
|@periodical| Numéro précis d’un périodique|
|@proceedings| Acte de colloque|
|@suppbook| Partie annexe d’un livre, comme par exemple la préface ou les appendices||
|@reference| Dictionnaire, encyclopédie, etc|
|@thesis| Thèse de doctorat, mémoire de maîtrise ou tout travail rédigen vue de l’obtention d’un titre scolaire ou universitaire.
|@unpublished| Ouvrage non publié|


### Quelques champs

Pour plus de champs, voir le manuel de `biblatex` p.17sq, ainsi que 
ROUQUETTE, Maïeul, [XeLaTeX appliqué aux sciences humaines](https://halshs.archives-ouvertes.fr/halshs-00924546), p.83 sq

*Champs de personnes*

- Les valeurs des champs de personnes sont de type "Prénom Nom" ou "Nom, Prénom". Pour considérer un ensemble de mot comme le "nom" (par exemple pour les auteurs antiques), le mettre entre accolades.
- Lorsqu'il y a plusieurs personnes dans un même champ, elles sont séparés par `and`

exemples: 
- `author = {Maïeul Rouquette and Enimie Rouquette and Brendan Chabannes}`

ou: `author = {Rouquette, Maïeul and Rouquette, Enimie and Chabannes, Brendan}`
-  `author  = {{Eugène de Tolède}}`


|Champ|Explication|
|-- |-- |
|annotator| Auteur(s) des annotations|
|author| Auteur(s) de l’œuvre|
|commentator| Auteur(s) des commentaires|
|editor| Éditeur(s) scientifique(s). On peut en préciser le rôle grâce au champ `editortype`|
|foreword| Auteur(s) de la préface|
|introduction| Auteur(s) de l’introduction|
|translator| Traducteur(s)|

Lorsque des champs possèdent des valeurs égales, biblatex fusionne ces champs lors de l’affichage. Par exemple, si `translator` et `editor` sont identiques, on obtient "édité et traduit par..."

*Champs de titre*

|Champ|Explication|
|-- |-- |
|booktitle| Titre du livre dans lequel l’entrée se situe|
|chapter| Chapitre d’un livre. Pour les entrées de type @inbook|
|issuetitle| Titre d’un numéro spécifique d’un périodique|
|journaltitle| Titre d’un périodique|
|maintitle| Titre d’une œuvre en plusieurs volumes|
|maintitleaddon| Ajout au titre d’une œuvre en plusieurs volumes|
|subtitle| Sous-titre de l’œuvre|
|title| Titre de l’œuvre|
|titleaddon| Ajout au titre de l’œuvre|


*Champs d'information sur la publication*

Pour plus de champs, voir le manuel et 
ROUQUETTE, Maïeul, [XeLaTeX appliqué aux sciences humaines](https://halshs.archives-ouvertes.fr/halshs-00924546), p.88 sq

|Champ|Explication|
|-- |-- |
|address| Lieu de publication.|
|date| Date de publication|
|edition| Numéro d’édition si plusieurs éditions existent|
|institution| Institution dans laquelle l’œuvre a été produite, pour les entrées de type @thesis|
|issue| Détail d’un numéro spécifique d’un périodique |
|number| Numéro d’un périodique ou numéro au sein d’une collection|
|origdate| Date de l’édition originale|
|origlanguage| Langue originelle|
|pagination|Le type de pagination (par défaut: `page`|
|pages| Pages de l’article ou de la partie du livre étudiée|
|publisher| Éditeur commercial|
|type| Pour les entrées de type @thesis, précise le type de travail|
|url| Url (adresse électronique) d’une publication en ligne|
|urldate| Date à laquelle une publication électronique a été consultée|
|volume| Volume dans une œuvre en plusieurs volumes|
|volumes| Nombre de volumes dans une œuvres en plusieurs volumes|



## Les styles bibliographiques

- Il est possible de charger différents styles pour les citations et pour la bibliographie, dans l'argument optionnel de l'appel du package:
	+ L'option `style=nom_du_style` charge à la fois le style de citation et le style bibliographique
	+ Les options `bibstyle=nom_du_style` et `citestyle=nom_du_style` chargent respectivement le style bibliographique et le style de citation

Exemples de style:

|Style|Description|
|-- |-- |
|numeric| chaque entrée se voit attribuer un numéro, qui est appellé lorsque l'on renvoie à cee entrée.|
|authortitle| sont indiqués seulement l'auteur et le titre de l’œuvre|
|verbose| la description complète de l’entrée est donnée la première fois, une version abrégée est affichée ensuite.|
|verbose-ibid| Comme verbose, mais avec l’abréviation *ibidem*|
|verbose-trad1, verbose-trad2, verbose-trad3|Comme verbose-ibid, mais avec également les abréviations *op. cit.*, *ibidem*, etc.|

Pour plus de précisions, voir le manuel p.74 sq

- Il existe un style de citations qui suit les normes de l'École des Chartes:
	+  [biblatex-enc](https://github.com/Jean-Baptiste-Camps/biblatex-enc)
	+ on peut l'installer dans son dossier `texmf local` (par exemple `/usr/local/texlive/texmf-local/tex/latex/biblatex-enc`) (voir le readme du style).
	+ **nb**: pour en apprendre plus sur l'arborescence d'une distribution TeX et ce que signifie `texmf local`, voir: [Guide pratique de Tex Live 2023](https://www.tug.org/texlive/doc/texlive-fr/texlive-fr.pdf) p.7, ou Daniel Flipo, [Admninistration d'une installation TeX](http://daniel.flipo.free.fr/doc/tex-admin/TeX-admin.pdf)
	+ On le passe ensuite en option à `biblatex`: `\usepackage[style=enc]{biblatex}`

- Pour que les œuvres anonymes soient classées en début de bibliographie, par titre, il faut utiliser le package `biblatex-anonymous`, et ajouter l'option `sorting` à l'appel du package  `biblatex`: 

```
\usepackage[style=enc,sorting=anonymous]{biblatex}
\usepackage{biblatex-anonymous}
```

**nb** l'appel du package `biblatex-anonymous` doit se faire après l'appel du package `biblatex`

## Imprimer sa bibliographie

- commande `\printbibliography`
- l'option `\nocite{#1}` permet d'imprimer dans la bibliographie des entrées non citées dans le corps du texte. L'argument peut-être soit un astérisque, pour indiquer que toutes les entrées du fichier .bib doivent être imprimées, soit une liste de clefs séparées par des virgules: `\nocite{*}`, `\nocite{clef1, clef2, clef3,...}`
- Il est possible de n'imprimer que des entrées ayant, ou n'ayant pas, un mot-clef:  options `keyword=xx` et `notkeyword=xx`; on peut de cette façon imprimer plusieurs sous-parties de bibliographie.

 Exemple: 

```
\printbibliography[keyword=sources-primaires]
\printbibliography[notkeyword=sources-primaires]
```

 D'autres choix sont possible (imprimer des bibliographies intermédiaires par exemple). Voir le manuel p. 90 et p. 140
- Pour modifier le titre de la ou des bibliographies: 
	+ dans le préambule, `\defbibheading{#1}{#2}`, où `#1`=une clef attribuée au titre et `#2` le titre
	+ dans l'argument optionnel de la commande `\printbibliography`, `heading=clef`

Exemple: 

```
\documentclass[a4paper]{book}
\usepackage{fontspec}
\usepackage{xunicode}
\usepackage{polyglossia}
\setmainlanguage{french}
\usepackage{biblatex}
\addbibresource{/home/user/Documents/memoire/bibliographie.bib}


\defbibheading{primaires}{\subsection*{Sources primaires}}
\defbibheading{secondaires}{\subsection*{Sources secondaires}}


\begin{document}
...
\section*{Bibliographie}
\printbibliography[heading=primaires, keyword=sources-primaires]
\printbibliography[heading=secondaires, notkeyword=sources-primaires]
\end{document}
```





## Zotero et LaTeX

###  Importer une bibliographie BibTex vers Zotero: 

- `Fichier-Importer` : 
	+  les clefs de citation restent telles quelles.
	+ les *keywords* sont importées dans "marqueurs"
- Remarques:
	+ certains champs bibtex  n'existent pas dans zotero. Ex: *maintitle*. Ils sont importés dans *extra* sous la forme: `tex.maintitle: XXX`. 
	+ Le formatage au sein d'un champ (des italiques par exemple) est possible au moyen de balises html. AInsi `\emph{xx}`devient `<i>xx</i>`

-> on peut exploiter ces possibilités pour donner plus de souplesse à Zotero

### Le module BetterBibTex

- Le module [BetterBibTex](https://retorque.re/zotero-better-bibtex/)  permet de répercuter dans un fichier BibTex les modifications apportées dans une collection (ou un ensemble de collections) gérée avec Zotero
- l’inverse n’est pas vrai : les modifications apportées dans le fichier BibTeX ne sont pas “remontées” dans Zotero.

Installation: 
1. télécharger le XPI file et le sauvegarder. **attention: sous firefox, faire clic droit et enregistrer la cible du lien** (un simple clic sur le lien ne marchera pas)
2. Dans zotero: `extension - ajouter depuis un fichier - installer - redémarrer zotero`
4. Configurer Betterbibtex pour l'exportation: `outils - betterbibtex -  ouvrir les preference de betterbitex`: 
-  onglet `exportation`: 
	-  decocher "exporter les caractères unicodes"
	-  choisir "ajouter les url à l'exportation dans le champs url"
	- onglet divers: décocher "appliquer la capitalisation aux titres"
- onglet `clef de citation`: possibilité de choisir la façon dont les clefs seront générées
3. Mettre en place la synchronisation  entre un fichier BibTex et une collection dans Zotero: faire un clic-droit sur la collection à exporter: `exporter - choisir betterbibtex` - cocher "garder à jour"

**RQ** Quand vous "aspirez" une référence bibliographique dans Zotero, pensez à vérifier que les informations sont bien entrées; vous pouvez utiliser le champs "extra" pour rajouter des champs propres à bibtex (voir supra)


