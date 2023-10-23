#  Outils pour la rédaction du mémoire (ENC 2314-2)

Vous trouverez sur ce dépôt le contenu pédagogique du cours *Outils pour la rédaction du mémoire*  du master Humanités Numériques  à l'Histoire à l'École des chartes.

## Planning

|Date|Programme|
|-- |-- |
|20/10|La recherche documentaire: catalogues et bases de données; Zotéro|
|27/10|LibreOffice; Introduction à LaTeX|
|24/11|LaTeX|
|01/12|LaTeX|
|08/12|LaTeX|
|15/12|LaTeX (fin); Git et le versionnage|


## Installation Zotero + Libreoffice sur linux en ligne de commande

Taper dans le terminal les commandes suivantes:

1.  Si snap n'est pas installé, installez-le: `sudo apt install snap`
1. `sudo snap install zotero-snap` 
2. `sudo apt install java-common` (si vous n'avez pas déjà installé java)
3. Si vous avez déjà libreoffice sans avoir installé java auparavant, désinstallez-le: `sudo apt remove libreoffice`
4. `sudo apt install libreoffice`
5. Ouvrez Zotero en tapant `zotero-snap` dans le terminal. Installez sur linux le connecteur internet en suivant les indications;  "aspirez" au moins une référence dans Zotero pour pouvoir tester.
6. Ouvrez libreoffice en tapant `libreoffice` dans le terminal.
7. Si les icônes de Zotero n'apparaissent pas dans la barre d'outilde libreoffice, allez dans Outils-Gestionnaire des extensions.  Cliquez sur Ajoutez;  allez sur les dossiers système (dossiers non visibles; il faut cliquer sur la petite flèche à gauche de votre nom avec la maison, puis sur la petite icône de disque-dur), et choisissez `/snap/zotero-snap/current/extensions/zoteroOenOfficeIntegration@zotero.org/install/Zotero_OpenOffice_Integration.oxt`
7. Redémarrez libreoffice.
8. testez en ouvrant libreoffice et cliquez sur l'icône Add/Edit Citation: une fenêtre "mise en forme rapide des citations" doit apparaître.


## Installation de LaTeX sur linux


### 1/ Pré-requis

Avoir le package `perltk` installé. Si ce n'est pas le cas:
- Ouvrez un terminal
- Tapez la commande suivante: `sudo apt install perl-tk` 


### 2/ Télécharger le programme d'installation

Deux possibilités: 

1. Téléchargez le fichier *via* le lien suivant: [install-tl-unx.tar.gz](https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz)
2. Dans le terminal, placez-vous dans le dossier Téléchargement par la commande `cd ~/Téléchargements` puis tapez `wget https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz`

Une fois le fichier téléchargé, décompressez-le. Pour cela,  tapez dans le terminal la commande `tar -xf install-tl-unx.tar.gz`


### 3/ Installer la texlive

1. Placez-vous dans le dossier que vous avez décompressé par la commande `cd` suivie du nom du dossier (`install-tl-20230926`; le nombre peut être différent). Vous pouvez utiliser la touche Tab pour activer l'autocomplétion du nom du dossier.
2. Tapez `sudo perl install-tl`
3. Si vous avez de la place sur votre ordinateur et une bonne connexion internet: répondez `i` ("start installation to hard disk"). **Cette option est à privilégier**
4. Si votre connexion est mauvaise, ou que vous avez trop peu de place, vous pouvez au choix:
	- tapez`c` pour sélectionner quelques collections de packages à décocher. Vous pouvez enlever sans problème les collections désignées par les lettres suivantes: `iklmnowxyzABCPS`. Attention, certaines collections seront utiles si vous comptez utiliser les langues concernées (par exemple arabe ou persan dans la collection `arabit`. Dans ce cas, ne les indiquez pas).
	- Si même ainsi cela prend trop de place/de temps, tapez `j` pour sélectionner un schéma et choisissez "teTex"   

	-> Tapez ensuite `r` pour retourner au menu principal, et `i` pour lancer l'installation.  
Il sera de toute façon possible d'installer plus tard ces collections si vous en avez besoin. 

### 4/ Configurer

Il ne reste plus qu'à configurer votre installation:

1. Tapez`sudo nano ~/.profile`
2. Dans le fichier qui s'ouvre, ajoutez à la fin les lignes suivantes: 

```
PATH=/usr/local/texlive/2023/bin/x86_64-linux:$PATH; export PATH
MANPATH=/usr/local/texlive/2023/texmf/doc/man:$MANPATH; export MANPATH
INFOPATH=/usr/local/texlive/2023/texmf/doc/info:$INFOPATH; export INFOPATH
```

3. Enregistrez le fichier, et tapez dans le terminal `source ~/.profile` pour que le changement soit pris en compte.
4. Vérifiez que tout fonctionne en tapant `which xelatex` dans le terminal: vous devez avoir le chemin de la texlive 2023 qui s'affiche.


### 5/ Installer un éditeur de texte (TexStudio)

Tapez dans un terminal la commande suivante: `sudo apt install texstudio` 

## Installer LaTeX sur les autres systèmes d'exploitation:

- Suivre les indications ici: [texlive](https://tug.org/texlive/).
- Installez [Texstudio](https://www.texstudio.org/)



