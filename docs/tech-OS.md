#<center>Linux Embarqué</center>  

## Quelques commandes utiles

`cd` -> change directory  
`cd .` -> on avance  
`cd ..` -> on recule  
`cd` - on retourne a la racine  
`ls` -> y a quoi la?  
`ls-la` -> y a quoi la avec des details sur les fichiers  
`cat` -> on lit ce qui a écrit dans un fichier  
`ln -s` -> on créer un lien symbolique  
`ln` pour lien  
`-s` pour symbolic  
`-h` pour hard link  
`echo` -> affiche ce que tu dis après   
(`echo "dbsuicbqs" > toto/fichier`) -> on met des trucs dans un fichier sans l'ouvrir  
`tree` -> joli affichage en arbre  

## Les opérations sur les fichiers

`CREATE`  
`DELETE`  
`OPEN`  
`CLOSE`  
`READ`  
`WRITE`  
`APPEND`  
`SEEK`  
`GET ATTRIBUTES`  
`SET ATTRIBUTES`  
`RENAME`  


## Stockage de données

Contiguê = les uns a la suite des autres  
Liste chainée = on indique le suivant  
Liste chainée indexée = on créer une table avec les adresses des blocs  memoires qui se suivent  


## Vocabulaire

Processus Zombie = processus dont le parent meurt, il ne peut donc pas être supprimer par le processus initial, il va bouffer de la ressource


## Exercice 2

5 processus A, B, C, D et E sont soumis à un calculateur dans cet ordre, mais quasi simultanément.
Ces travaux ne font pas d'entrées-sorties. Leurs durées respectives sont 10, 6, 2, 4 et 8 secondes.

Déterminer les temps de réponse de chacun des processus, ainsi que le temps de réponse moyen,
pour les disciplines FIFO (First In First Out) et SJF (Shortest Job First)

A = 10
B = 16
C = 18
D = 22
E = 30

Temps de réponse moyen : (10+16+18+22+30)/5 = 19,2s


Même question pour une discipline à priorité, avec P(A)=3, P (B)=5, P(C)=2, P(D)=1, P(E)=4 avec le
plus petit chiffre égal à la priorité la plus forte.

D = 4
C = 6
A = 16
E = 24
B = 30

Temps de réponse moyen : (4+6+16+24+30)/5 = 16s


## Expressions régulières

Les expressions régulières caractérisent uniquement des chaînes de caractères et
non pas des noms de fichiers.

***

## Exercice 1

Afficher l’ensemble de vos variables d’environnement : printenv
Donner la signification de:
      PATH = lien de tous les executables executable partout
      PS1 = info sur le prompt
      HOME = Directory de base de l'utilisateur
      TERM = Configuration du terminal

`env | grep "TERM"`
`echo $TERM`

Quels sont les alias présents sur votre machine?

`alias >> maindell/Dropbox/Cours/OS/TP1.txt`  

`alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'`  
`alias egrep='egrep --color=auto'`  
`alias fgrep='fgrep --color=auto'`  
`alias grep='grep --color=auto'`  
`alias l='ls -CF'`  
`alias la='ls -A'`  
`alias ll='ls -alF'`  
`alias ls='ls --color=auto'`  
  
Créer un alias lu qui réalise la commande ls -lrt?
`alias lu='ls -lrt'`  
  
Le rendre permanant
`echo "alias lu='ls -lrt'" >> ~/.bash_aliases`
  
Supprimer cet alias
`unalias lu`
  
Créer, dans votre environnement de travail, l’arborescence suivante :
```
SE    
    /TP1  
      /doc
      /script
      /delivery
    /TP2  
      /bin
      /obj
      /src
      /inc
```

`mkdir -p SE/{TP1/{doc,script,delivery},TP2/{bin,obj,src,inc}}`

Afficher son répertoire courant
`pwd`

Créer le fichier bonjour.c sous SE/TP2/src contenant les lignes suivantes :
```
// directive du préprocesseur
#include <stdio.h>

/* prototype des fonctions */
/* programme principal */
main(){
printf(« Bonjour\n ») ;
/*
0100123456123
0100123457123
0100123458123
0100123459123
0100123450123
0100123451123
0100123451123
*/
}

cd ~/Dropbox/Cours/OS/SE/TP2/src
touch bonjour.c
echo "// directive du préprocesseur
#include <stdio.h>
/* prototype des fonctions */
/* programme principal */
main(){
printf(« Bonjour\n ») ;
/*
0100123456123
0100123457123
0100123458123
0100123459123
0100123450123
0100123451123
0100123451123
*/
}" >> bonjour.c
```
  
Déplacer vous sous votre home directory et créer le fichier vide config.txt  
`cd ~`  
`touch config.txt`  
  
Déplacer vous par un déplacement absolu sous le répertoire src et compiler le programme  
bonjour.c en un programme exécutable bonjour. Le résultat de la compilation est déplacé sous bin.  
`cd ~/Dropbox/Cours/OS/SE/TP2/src`
`gcc bonjour.c -o ~/Dropbox/Cours/OS/SE/TP2/bin/bonjour`
  
Afficher les types des fichiers bonjour et bonjour.c
`ls -lrt`
  
Déplacez vous par un déplacement relatif sous bin
`cd ..`  
`cd bin/`  

Modifier les droits du fichier bonjour afin qu’il soit:
  - en lecture, écriture, exécution pour le owner
  - en lecture, exécution pour le groupe
  - et non accessible pour les autres.
`chmod 750 coucou`
  
Déplacez vous sous votre home directory et modifiez de façon récursive l’ensemble des droits (directories + fichiers) de TP2  
`cd ~`  
`find ./Dropbox/Cours/OS/SE/TP2 -type d -exec chmod 751 {} \;`  
`chmod -R 750 /Dropbox/Cours/OS/SE/TP2`  
  
Copier le fichier bonjour.c en salut.c en local,  
`cp bonjour.c salut.c`  
  
Copier le répertoire TP2 en TP3 avec l’ensemble de ses fichiers,  
`cp -R /Dropbox/Cours/OS/SE/TP2 /Dropbox/Cours/OS/SE/TP3`
  
Déplacer le fichier salut.c de TP3 dans SE/TP2/src en l’appelant salut1.c,  
`mv /Dropbox/Cours/OS/SE/TP2/src/salut.c /Dropbox/Cours/OS/SE/TP3/src/salut1.c`
  
Effacer le fichier bonjour.c de TP3,  
`rm /Dropbox/Cours/OS/SE/TP3/src/bonjour.c`
  
Effacer TP3  
`rm -R /Dropbox/Cours/OS/SE/TP3`
  
Copier le répertoire TP2 en TP3 avec l’ensemble de ses fichiers  
`cp -R /Dropbox/Cours/OS/SE/TP2 /Dropbox/Cours/OS/SE/TP3`
  
Changer les droits du fichier salut.c de TP3 en _rwxrwxrwx  
`chmod 777 /Dropbox/Cours/OS/SE/TP3/src/salut.c`
  
Changer le owner de ce fichier par le nom de login de votre voisin(e), monitorer le résultat,  
`chown root /Dropbox/Cours/OS/SE/TP3/src/salut.c`
  
Changer le groupe de ce fichier par un groupe connu sur la machine,  
`chgrp root /Dropbox/Cours/OS/SE/TP3/src/salut.c`
  
Attribuer les droits rwxrwxrwx à TP3 et aux fichiers qu’il contient,  
`chmod -R 777 /Dropbox/Cours/OS/SE/TP3`
  
Changer en une seule commande le owner et groupe de TP3 et des fichiers qu’il contient,  
`chown root:root /Dropbox/Cours/OS/SE/TP3`
  
Se positionner sur son home directory et créer un lien symbolique vers le fichier salut.c de TP3.  
`cd`  
`ln -s /Dropbox/Cours/OS/SE/TP3/salut.c`
  
Editer ce lien. Expliquer la différence entre un lien permanent et un lien symbolique.  
`cat /Dropbox/Cours/OS/SE/TP3/salut.c`
  
Afficher de trois façons différentes le contenu du fichier bonjour.c  
cat, nano, vi
  
Afficher le contenu de votre PATH,  
`$PATH(/home/maindell/bin:/home/maindell/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games)`
  
Modifier le contenu de la variable d’environnement PATH afin d’y ajouter le répertoire local.
`export PATH=/Dropbox/Cours/OS/SE/TP2/bin:$PATH`
  
Vérifier que, situez sous SE/TP2/bin, vous pouvez lancer bonjour de la façon suivante :  
bonjour
Oui
  
( Attention de ne pas effacer PATH)  
Modifier votre profil utilisateur afin de modifier PATH comme précédemment.  
  
Modifier votre prompt afin d’afficher [<votre_user>@<hostname> : <le repertoire_courant>] >  
`export ps1 mes couilles`
  
Déplacez vous sous SE/TP1/script et créer, en 1 seule commande, un fichier essai.bash contenant #!/bin/bash  
`cd /home/maindell/Dropbox/Cours/OS/SE/TP1/script`  
`echo '#!/bin/bash' >> /home/maindell/Dropbox/Cours/OS/SE/TP1/script/essai.bash`  
  
Ajouter à la fin de essai.bash la ligne « ls –lrt » (en une seule commande)  
`echo 'ls -lrt' >> essai.bash`


Sur le shell 1, affichez la fin du fichier essai.bash avec mise à jour,  
`tail -f essai.bash`
  
Rechercher l’occurrence « include » dans le fichier bonjour.c  
`grep 'include' /home/maindell/Dropbox/Cours/OS/SE/TP2/src/bonjour.c`
  
Afficher l’ensemble des processus utiliser par root, puis par votre user,  
`ps -U root`
  
Afficher l’ensemble des sockets utilisées par votre machine,  
`netstat`
  
Afficher l’ensemble des sockets en état ‘ESTABLISHED’ sur votre machine.  
`netstat | grep 'ESTABLISHED'`
  
Affichez le nombre de sockets en état ‘ESTABLISHED’  
`netstat | grep 'ESTABLISHED' | wc -l`  
`netstat | grep -c 'ESTABLISHED'`
  
Changer votre password  
`passwd`
  
Rechercher à partir de votre home directory l’ensemble des fichiers .c contenus dans ce répertoire et ses sous répertoires  
`find / -name '*.c'`
  
Rechercher à partir de votre home directory l’ensemble des fichiers .c contenant le caractère ‘u’ dans leur nom,  
`find / -name '*u.c'`
  
Rechercher à partir de votre home directory l’ensemble des occurrences de « printf » dans l’ensemble des fichiers .c contenus dans ce répertoire et ses sous répertoires,  
``find -name '*.c' -exec grep 'println' {} \; -print`
  
Rechercher à partir de votre home directory l’ensemble des fichiers qui ne sont pas d’extension.c  
`find / -not -name '*.c'`
  
Modifier l’ensemble des fichiers contenu dans votre répertoire courant et ses sous-répertoires d’extension .bak en .c  
`rename s/.bac/.c/ *.bac`
  
Afficher dans un fichier le contenu de l’ensemble des fichiers .c se trouvant sous ./SE/TP2/src.  
`ls *.c |xargs cat > /home/maindell/Dropbox/Cours/OS/SE/retour.txt`
  
Afficher qui est loggé sur votre machine ?  
`who`
  
Afficher qui est loggé sur votre machine sur la sortie standard mais également dans un fichier log.txt (sans répétition de commande) ?  
`who>exo.log`
  
Afficher quel est le nom de votre machine ?  
`uname -a`

Afficher quel est le nom de votre système ?  
`uname`
  
Afficher quel est le nom du terminal associé à votre user ?  
`tty`
  
Afficher les numéros utilisateurs et groupe  
`id`
  
Monitorer de manière dynamique l’ensemble des process (rafraichissement de la commande 2 secondes),
  
Lancer un process en background,  
`firefox &`


Monitorer le de 2 façon différentes,  
`ps`
  
Tuer le violemment.  
`kill 1`
  
Lancer un process, l’interrompre et le mettre en exécution en background,
firefox  
`CTRL+Z`  
`bg`
  
Monitorer le,  
`ps`
  
Basculer ce process en foreground,  
`jobs`  
`fg1`
  
Stopper le par un signal d’interruption.  
`CTRL+C`
  
Transformer les commentaires // en /* */ – Affichage stdout  
`sed -e 's/\/\/\(.*\)/\/* \1 *\//g' TP2/src/bonjour.c>salut.C`  
`sed -e 's://\(.*\):/* \1 */:g' TP2/src/bonjour.c>salut.C`  
g pour dire qu'on fait ça sur toutes les lignes
  
Exo chiant
```
awk 'BEGIN {FS=":" ; OFS='@'} {print "Affichage de la ligne "NR" avant modification: "$0} $7!="" {print "Shell trouve ligne "NR" : "$7" remplace par /bin/bash" ; $7="/bin/bash"} $6="" {print "Usenr directory trouve ligne "NR" : "$6" (User : "$1" "} {print "Ligne "NR" apres modification : "$0"} ' /etc/passwd
```