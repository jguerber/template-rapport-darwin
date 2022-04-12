# Un template TeX pour les consignes du rapport de stage

## Installation

Attention au compilateur de biblio : biber marche mais pas biblatex. Normalement il est installé de base dans les versions récentes de MixteX (windows) ou Texlive (linux).

Pour être sûr que tout fonctionne, il faut compiler avec pdflatex, puis biber, puis pdflatex deux fois (soit manuellement par le terminal ou par le quick build de ton éditeur de texte favori). Louis a trouvé [un tuto pour forcer TexMaker à utiliser biber](https://tex.stackexchange.com/questions/154751/biblatex-with-biber-configuring-my-editor-to-avoid-undefined-citations/154788).

## Comment faire des modifs

Si ça vous motive on peut s'entraîner à utiliser la manière classique sur GitHub : d'après ce que j'ai compris c'est de "fork" le repo depuis github (ça crée une copie du repo dans ton propre compte github), de bosser sur son fork et quand on a un ensemble de modifications qu'on trouve cool on peut ouvrir une pull request pour en discuter et les intégrer.

Sinon une manière plus simple c'est d'ajouter des "collaborators" pour que chacun.e clone ce repo là et que tout le monde push/pull directement ici.

## Le style de biblio

Pour mettre un astérisque devant les publis importantes, j'ai trouvé [ça](https://github.com/jguerber/template-rapport-darwin/blob/main/main.tex#L62-L67), ça marche en rajoutant `options = {extsym={*}}` dans les articles concernés dans le fichier .bib.

Pour la phrase de description c'est basé sur deux discussions sur stackexchange ([ici](https://tex.stackexchange.com/questions/149578/how-to-comment-references-in-a-bibliography) pour le principe et [ici](https://tex.stackexchange.com/questions/238554/data-model-macro-cannot-be-used-in-preamble?noredirect=1#comment566230_238554) pour s'adapter aux nouvelles versions de biber). Dans main.tex ça donne [ça](https://github.com/jguerber/template-rapport-darwin/blob/main/main.tex#L83), en ajoutant `mynote = {la phrase à rajouter}` dans le fichier .bib.

## Pistes d'améliorations

* Avoir une numérotation différente pour les figures et tableaux du texte général et les figures et tableaux de l'annexe
* Changer le style des citations et de la biblio ? Je pense à la police en majuscules qui est un peu étrange
* Faire une page de titre qui copie leur modèle ? Pas forcément nécessaire mais ça piquerait moins les yeux
