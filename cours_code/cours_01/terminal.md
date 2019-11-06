
### 1\. Introduction

Accroche-toi à tes chaussettes, car nous allons maintenant découvrir les bases du terminal ! Il s'agit d'un outil très puissant permettant de "parler" à son ordinateur. Nous allons voir : comment interagir avec le terminal, comment jouer avec ses premiers fichiers, et bien d'autres choses utiles. C'est plutôt fun, tu vas voir !

#### 1.1. Ce que tu vas apprendre dans cette ressource

Voici la liste des questions auxquelles tu vas pouvoir répondre avec cette ressource :

* Qu'est-ce que le terminal ?
* Que veulent dire GUI et CLI ?
* Comment lancer un terminal ?
* Comment exécuter ses premières fonctions avec un terminal ?
* Pourquoi la notion de géographie est très importante dans un terminal ?
* Qu'est-ce que VIM et comment s'en servir ?

### 2\. Historique

Le terminal -- ce que l'on appelle plus communément un _interpréteur de commande_ (ou command-line interpreter - CLI - en anglais) -- est un outil qui interprète les commandes tapées au clavier dans l'interface de ligne de commande.

À la base, les ordinateurs tournaient sans interface graphique. Les utilisateurs n'avaient donc pas d'autre choix que de passer par les CLI pour effectuer une action. L'arrivée des systèmes d'exploitation graphiques (Windows, Apple, Linux) n'a pourtant pas tué la popularité de la CLI car il permet de faire des tâches extrêmement précises.

En gros, c'est une version texte de l'explorateur de fichiers : on peut ouvrir des dossiers, créer des fichiers, les lancer, les renommer, installer des programmes, et bien d'autres choses. On dit que c'est une **CLI** (Command Line Interface), comparée à la **GUI** (Graphical User Interface) de l'explorateur normal. Tout est fait via le clavier, donc pas besoin de souris pour l'utiliser.

### 3\. Le terminal

#### 3.1. Qu'est-ce que le terminal ?

Le terminal est un outil intimidant aux premiers abords, mais pas si compliqué au final. J'ai réalisé une vidéo pour l'expliquer :

#### 3.2. Comment le lancer ?

##### 3.2.1. Sur macOS

`CMD` \+ `SPACE`, puis écrire `Terminal` (ou iTerm), `Enter`.

##### 3.2.2. Sur Linux

`CTRL` \+ `ALT` \+ `T`.

#### 🚀 ALERTE BONNE ASTUCE

Si tu utilises Linux, passe ton terminal en anglais. Ça va vraiment t'aider lorsqu'il te renverra des erreurs. En effet, comme l'anglais est la langue d'internet, la majorité des gens ayant eu ton problème vont le poster en anglais. Tu auras ainsi 100 fois plus de résultats sur Google qu'avec une erreur postée en français.

##### 3.2.3. Sur Windows

Sur Windows, le terminal sera géré de manière un chouilla différente. Pendant toute la formation, nous allons utiliser un terminal de type [Shell Unix][1], car c'est le plus utilisé au monde et qu'il sera donc plus aisé pour toi de trouver des réponses en cas de problème. Le terminal _Shell Unix_ est celui qui est installé de base pour Linux et macOS. Celui de Windows est l'invite de commandes, qui est de type DOS. Bon je sais, ça commence à faire beaucoup d'infos... Mais essaie au moins de retenir ces points :

* macOS et Linux utilisent le même "noyau" de système d'exploitation : Unix ; tandis que Windows utilise DOS.
* Le terminal de macOS et Linux est de type Shell Unix, tandis que celui de Windows est de type DOS. Ce qui fait que l'invite de commandes de Windows aura une utilisation différente de celui de type Unix Shell.
* Dans le milieu de la programmation, le terminal de type Shell Unix est universellement utilisé.
* Si tu es utilisateur de Windows, nous te demanderons de trouver une alternative à l'invite de commandes.

Pas de panique, nous avons pensé à toi si tu es sur Windows ! Voici quelques alternatives qui feront le travail :

* La solution de facilité pour les grands débutants du terminal est [Cygwin][2]. Pour t'aider, j'ai même réalisé [une vidéo tutorielle][3] pour son installation.
* C'est en constatant le rejet universel de Windows chez les développeurs qu'un certain Satya Nadella a travaillé dur pour proposer une alternative décente. Ainsi, **si tu es sur Windows 10**, il existe un terminal Shell Unix qui s'appelle _Windows Subsystem for Linux_ et qui installe une version de Linux sur Windows dont tu peux te servir

#### 3.3. Premières fonctions ?

Pour faire marcher le terminal, rien de plus simple : il suffit de rentrer le texte correspondant à une fonction pour que celle-ci s'exécute. Par exemple, si dans l'explorateur en GUI il suffit de double cliquer sur `mon_fichier.txt` pour l'ouvrir, il faudra taper `open mon_fichier.txt` (sur macOS) ou `xdg-open mon_fichier.txt` (sur Linux) dans le terminal pour faire de même. On va tester ça avec notre première fonction :
    
    
    $ echo "Hello world !"

_(je commence toutes les commandes de terminal avec un `$`. C'est une convention qui aide à reconnaître les commandes de CLI, mais qui ne fait pas partie de la commande. Enlève donc bien le $ au moment de tester !)_

Si tu exécutes cette commande, le terminal devrait te renvoyer `Hello world !` (cette phrase est [un grand classique de la programmation][4]). Et là, BOUM ! Tu viens d'exécuter ta première commande de terminal 🎉.  
Maintenant nous allons voir quelques commandes basiques.

##### 3.3.1. PWD

`pwd` est l'acronyme de Print Working Directory, une commande affichant le dossier dans lequel tu es actuellement.
    
    
    $ pwd

Pour moi, `pwd` me renvoie :
    
    
    /Users/felix

C'est comme dans l'explorateur en GUI, quand tu double-cliques sur `felix`, il te déplace dans le dossier `felix` qui est dans le dossier `Users`.

#### 🚀 ALERTE BONNE ASTUCE

`pwd` est généralement la première commande que l'on tape quand on arrive dans le terminal de quelqu'un car c'est idéal pour s'y retrouver ✌️

##### 3.3.2. LS

`ls` est le diminutif de _list_. Cette fonction affiche les fichiers et dossiers situés dans mon dossier actuel.
    
    
    $ ls

Pour moi, `ls` me renvoie :
    
    
    Applications/   Dropbox/     Music/       Desktop/
    Pictures/     Documents/    Library/     Public/
    Downloads/    Movies/

Dans le terminal, nous pouvons ajouter des options à la plupart des fonctions en utilisant la syntaxe `$ fonction -option`. Par exemple, je peux faire `ls -a` (a pour "all"), ce qui a pour effet d'afficher aussi les fichiers commençant par un `.` (fichiers de devs en général). Je peux faire `ls -l` pour afficher la liste au format long. Et je peux même combiner les deux en faisant `ls -al`.

##### 3.3.3. MAN

`man` est le diminutif de _manual_. Man lance un programme permettant de lire le manuel d'une fonction précise. Pratique pour connaître toutes ses spécificités ! Pour s'en servir, il suffit de taper : `man fonction`. Par exemple, pour afficher le manuel de la commande ls, je dois taper :
    
    
    $ man ls

Cette commande m'ouvrira le manuel de ls, que je peux quitter à tout moment en tapant `q` (comme... "quit").

#### 3.4. Où sommes-nous ?

La notion de géographie est **fondamentale** pour le terminal. Tout comme dans l'explorateur en GUI, on se déplace aussi de dossiers en dossiers dans le terminal. Si jamais tu veux ouvrir un fichier en tapant `open file.txt` (sur macOS) ou `xdg-open file.txt` (sur Linux) et que tu ne te trouves pas dans le bon dossier, le terminal te renverra une erreur. C'est un peu comme si tu essayais de double-cliquer sur file.txt dans le mauvais dossier : impossible, car il n'y est pas.

Tu vas donc devoir te déplacer de dossiers en dossiers pour ouvrir et interagir avec les bons fichiers.

#### 3.5. CD

`cd` est l'acronyme de _Change Directory_. Cette commande permet de naviguer entre dossiers. Il s'agit en quelque sorte d'un double-clic sur un dossier 😁
    
    
    $ cd nomdudossier

Tu te déplaceras dans le dossier nommé `nomdudossier` (s'il existe là où tu te trouves).

Tu peux aussi te déplacer vers le dossier parent en faisant `$ cd ..`

#### 🚀 ALERTE BONNE ASTUCE

Utiliser la touche `TAB` permet de faire de l'autocompletion, très pratique pour cette méthode. Aussi, faire `cd` \+ [ESPACE] + `TAB` \+ `TAB` affiche les dossiers disponibles.

#### 3.6. Autres fonctions

##### 3.6.1. Créer un fichier

En tapant :
    
    
    $ touch nomdufichier

Cette commande va créer un fichier qui s'appelle _nomdufichier_

##### 3.6.2. Copier

Pour copier un fichier ou un dossier et le coller ailleurs, il suffit de rentrer :
    
    
    $ cp fichier_à_copier lieu_de_destination

##### 3.6.3. Déplacer

Pour déplacer (couper) un fichier ou un dossier d'un endroit vers un autre, il suffit de rentrer :
    
    
    mv [fichier_à_déplacer] [lieu_de_destination]

#### 🚀 ALERTE BONNE ASTUCE

`mv` (diminutif de "move") est très pratique pour renommer un fichier. Imaginons que tu as créé un fichier "hello.rv" au lieu de "hello.rb". Oups, malheur ! Heureusement, faire `$ mv hello.rv hello.rb` résout ce petit incident en quelques coups de clavier !

##### 3.6.4. Remove

Supprimer un fichier :
    
    
    $ rm nomdufichier

Il est possible d'effacer un dossier ainsi que son contenu en ajoutant `-r` (comme "recursion") en option : 
    
    
    $ rm -r nomdudossier

#### 📚 INSTANT CULTURE GÉ

`rm` est à l'origine d'une blague vieille comme le monde. En effet, ajouter l'option `-f` permet de forcer la suppression d'un fichier, même s'il est important pour l'ordinateur. D'autre part, finir par `/` ou `*` dit à votre ordinateur d'inclure absolument tous les fichiers. Ainsi, si tu tapes `$ rm -rf /` ou `$ rm -rf *` dans ton terminal, tu dis à ce dernier de tout prendre et de tout effacer, en forçant les barrières. En plus, figure-toi que `rm` est très rapide. Il effacera donc l'intégralité de ton ordinateur en quelques secondes à peine ! Conclusion : **à ne jamais jamais jamais faire**.

##### 3.6.5. Vim

Vim est l'un des éditeurs de texte les plus respectés au monde. Comme il passe uniquement par le terminal, il se marie extrêmement bien avec cet outil. Et comme il utilise juste le clavier, ses raccourcis permettent d'aller vraiment vite pour qui ose grimper la très rude courbe d'apprentissage (quelques semaines à plein temps). De ce fait, je te montrerai vim pour ta culture G, mais te demanderai de passer par un autre éditeur de texte 😉
    
    
    $ vim nomdufichier

Cette commande permet d'ouvrir vim sur le fichier _nomdufichier_ et de l'éditer. Pour quitter vim, il faut rentrer `:q!`.

#### 3.7. Autres astuces

`CTRL` \+ `C` annule la fonction en cours. Pratique quand on a une boucle infinie !

La casse est très importante, idem pour les espaces.

Il y a des raccourcis pratiques, comme par exemple `CTRL` \+ `U` qui efface la ligne en cours.

Les touches du haut et du bas permettent de naviguer dans l'historique des commandes. Super pratique pour exécuter à nouveau une commande que tu viens de taper.

### 4\. Points importants à retenir

Voici les points à retenir de la ressource :

* Pour lancer le terminal sur Linux : `CTRL` \+ `ALT` \+ `T` ; pour le lancer sur macOS : `CMD` \+ `SPACE`, puis écrire `Terminal` (ou iTerm) et presser la touche Enter ; pour Windows il te faudra trouver un subterfuge : [Cygwin][3] est la solution parfaite pour les débutants.
* `man` permet de lancer le manuel des fonctions.
* `pwd` affiche le dossier dans lequel tu es actuellement.
* `ls` est une commande qui affiche les fichiers et dossiers contenus dans mon dossier actuel.
* La notion de géographie est fondamentale : le terminal n'arrivera pas à ouvrir les fichiers s'il ne se trouve pas dans le bon dossier.
* `cd` permet de changer de dossier.
* `touch` permet de créer un fichier.
* `cp` permet de copier un fichier.
* `mv` permet de déplacer un fichier ou un dossier.
* `rm` permet de supprimer un fichier.
* `rm -r` permet de supprimer un dossier et son contenu.

### 5\. Aller plus loin

Voici un excellent [cours express][5] pour avoir quelques bases concernant l'utilisation du terminal. Il est un peu similaire au mien, mais aborde d'autres sujets intéressants tels que le PATH.

Viking Code School ont aussi fait un [cours sur le pimp de terminal][5] pour y intégrer de couleurs de BGs.

Michael Hartl a fait une célèbre introduction au terminal nommée [Learn Enough Command Line to Be Dangerous][6]. Cette ressource permet d'aller assez loin dans les détails de l'utilisation du terminal.

Pour ceux qui veulent découvrir Vim, voici [une marche à suivre][7] pour être champion de Vim rapidement.

[1]: https://fr.wikipedia.org/wiki/Shell_Unix
[2]: https://www.cygwin.com/
[3]: https://youtu.be/YogNpgcKY9A
[4]: https://fr.wikipedia.org/wiki/Hello_world
[5]: https://www.vikingcodeschool.com/web-development-basics/a-command-line-crash-course
[6]: https://www.learnenough.com/command-line-tutorial
[7]: https://medium.com/actualize-network/how-to-learn-vim-a-four-week-plan-cd8b376a9b85
