# Un template TeX pour les consignes du rapport de stage

## Installation

Attention au compilateur de biblio : biber marche mais pas biblatex. Normalement c'est installé de base dans les versions récentes de MikTeX (windows) ou Texlive (linux).

Pour être sûr.e que tout fonctionne, il faut compiler avec pdflatex, puis biber, puis pdflatex deux fois (soit manuellement par le terminal, soit par le quick build de ton éditeur de texte favori). Louis a trouvé [un tuto pour forcer TexMaker à utiliser biber](https://tex.stackexchange.com/questions/154751/biblatex-with-biber-configuring-my-editor-to-avoid-undefined-citations/154788).

## Structure des fichiers

* la structure générale et les options de formattage dans main.tex
* des définitions de styles (couleurs, trucs soulignés) dans style/style.tex. On peut même le passer en .gitignore pour que chacun puisse avoir sa version perso sans devoir rechanger le fichier à chaque `pull`
* les chapitres à inclure avec `\input` dans chapters .tex. J'aime bien faire ça parce que ça sépare un peu le corps du texte du code de formattage

## Comment faire des modifs

Si ça vous motive on peut s'entraîner à utiliser la manière un peu "générale" sur GitHub : d'après ce que j'ai compris c'est de "fork" le repo depuis github (ça crée une copie du repo dans ton propre compte github), de bosser sur son fork et quand on a un ensemble de commits qu'on trouve cool on peut ouvrir une pull request pour en discuter et les intégrer.

Sinon une manière clairement plus simple c'est d'ajouter des "collaborators" pour que chacun.e clone ce repo là et que tout le monde push/pull directement ici (avec des potentiels conflits de merge du coup mais tranquille).

J'ai activé l'onglet "discussions" pour avoir un endroit où parler (attention c'est public, tout internet y a accès, dont la CIA, les profs et vos darons).

## Le style de biblio

Pour mettre un astérisque devant les publis importantes, j'ai trouvé [ça](https://github.com/jguerber/template-rapport-darwin/blob/main/main.tex#L62-L67), ça marche en rajoutant `options = {extsym={*}}` dans les articles concernés dans le fichier .bib.

Pour la phrase de description c'est basé sur deux discussions sur stackexchange ([ici](https://tex.stackexchange.com/questions/149578/how-to-comment-references-in-a-bibliography) pour le principe et [ici](https://tex.stackexchange.com/questions/238554/data-model-macro-cannot-be-used-in-preamble?noredirect=1#comment566230_238554) pour s'adapter aux nouvelles versions de biber). Dans main.tex ça donne [ça](https://github.com/jguerber/template-rapport-darwin/blob/main/main.tex#L83), en ajoutant `mynote = {la phrase à rajouter}` dans le fichier .bib.

## Pistes d'améliorations (non exhaustif)

* Avoir une numérotation différente pour les figures et tableaux du texte général et les figures et tableaux de l'annexe
* Pour l'instant j'utilise des titres de sections pas numérotés et je les rajoute ensuite à la table des matières manuellement (cf les commentaires de chapters/abstract.tex). Avec un `\newcommand` qui ferait ça tout seul ça serait moins lourd à écrire et ça permettrait que chacun.e puisse numéroter ou pas ses sections selon ses préférences
* Vérifier que tous les critères des profs sont remplis
* Changer le style des citations et de la biblio ? Je pense à la police en majuscules qui est un peu étrange
* Faire une page de titre qui copie leur modèle ? Pas forcément nécessaire mais ça piquerait moins les yeux
