Projet: cryptage de fichier à l’aide de l'algorithm RC4

L'objectif du projet est de comprendre l'étendu des problématiques qui peuvent être rencontrés
lors de la réalisation d'un logicielle parallèle, ainsi que d'adopter une stratégie pour la parallélisation du logiciel.

Une partie théorique est également à mettre en application (loi d'Amdahl).
Les ordinateurs d'aujourd'hui sont composés d'un grand nombres de coeurs de calculs. Il est
aujourd'hui crucial pour un développé de savoir utiliser l'intégralité des ressources d'une
machine.

Le projet consiste à développer une application capable de crypter et de décrypter un fichier.
Ceci doit être réalisé avec l'utilisation de threads afin de profiter d'une accélération
non-négligeable.

Le projet devra être réalisé en en C++ et devra utiliser les outils CMake et Make pour compiler.
Les commandes suivantes sont exécutées depuis la racine de votre projet.
Votre application devra s’utiliser de la manière suivante:

$ ./main
main {-e|-d} NB_THREADS INPUT_FILE OUTPUT_FILE
$ mkdir build && cd build && cmake .. && make
$ ls
main myfile
$ ./main -e 2 myfile myfile.rc4
$ ls
main myfile myfile.rc4
$ ./main -d 2 myfile.rc4 myfile.rc4.decrypt
$ ls
main myfile myfile.rc4 myfile.rc4.decrypt
$ shasum myfile myfile.rc4.decrypt
13186770ec555445abd9e1c50a39cb6be517f312 myfile
13186770ec555445abd9e1c50a39cb6be517f312 myfile.rc4.decrypt
Le programme devra sortir, en mode release, uniquement un fichier correspondant au fichier
d’entré. Avec l’option ‘-e’ le fichier de sortie se verra suffixé de l’extension ‘.rc4. Avec l’option ‘-d’
le fichier de sortie se verra suffixé de l’extension ‘.decrypt.
Le rendu du projet devra se faire par MyGES sous la forme d’une archive zip . Cette archive
devra être structuré de la façon suivante:
/CMakeLists.txt
/src/
/doc/

Un suivi de projet sera effectué le 16 novembre 2018 . Ce suivi devra contenir:
- Une présentation du problème
- Liste des librairies utilisés
- Méthodologie de test
- Code sequentiel avec tests
- Version alpha parallèle avec tests

Un rapport de projet est à rendre le 7 décembre 2018 et doit comprendre:
- Une présentation du problème
- Stratégie utilisé pour la parallélisation
- Calcul du speedup théorique (Loi d’Amdahl) et mesuré
- Difficultées rencontrés
- Explication des flags de compilation utilisé dans CMake4

Le code source devra compiler sans erreur et sans warnings . Celui-ci sera compilé sur la machine cible.
Pour information, le matériel sur lequel votre code sera compilé et exécuté sera un noeud de calcul qui aura comme configuration:
- Linux Ubuntu 14.04
- 2 x Intel Xeon CPU E5-2699 v3 @ 2.30GHz
- 120Go RAM
- g++ version 4.9.4

Points bonus :
- Pour les groupes qui feront une compression et une décompression le plus rapidement
- Code propre et orienté objet

Note : Aucun plagiat ne sera autorisé. Tout projet s’inspirant de trop près de github ou de stackoverflow se verra pénalisé.