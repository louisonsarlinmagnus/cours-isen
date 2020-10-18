QUELQUES COMMANDES DE CONSOLES
------------------------------
cd -> change directory

cd . -> on avance
cd .. -> on recule
cd - on recule qu'une fois

ls -> y a quoi la?

ls-la -> y a quoi la avec des details sur les fichiers

cat -> on lit ce qui a écrit dans un fichier

ln -s -> on créer un lien symbolique
ln pour lien
-s pour symbolic
-h pour hard link

echo -> affiche ce que tu dis après 
(echo "dbsuicbqs" > toto/fichier) -> on met des trucs dans un fichier sans l'ouvrir

tree -> joli affichage en arbre

QUOI QU'ON PEUT FAIRE SUR UN FICHIER
------------------------------------

CREATE
DELETE
OPEN
CLOSE
READ
WRITE
APPEND
SEEK
GET ATTRIBUTES
SET ATTRIBUTES
RENAME

STOCKAGE DE DONNÉES
-------------------

Contiguê = les uns a la suite des autres
Liste chainée = on indique le suivant-
Liste chainée indexée = on créer une table avec les adresses des blocs memoires qui se suivent


VOCABULARE
----------

Processus Zombie = processus dont le parent meurt, il ne peut donc pas être supprimer par le processus initial, il va bouffer de la ressource



EXERCICE 2
----------

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


Même question avec la discipline PS (Proc. Sharing - Tourniquet) et un quantum de 2 s.

 |0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|24|25|26|27|28|29|30|
A|xxxxx|             |
B|
C|
D|
E|



EXPRESSION RÉGULIÈRES
---------------------

Les expressions régulières caractérisent uniquement des chaînes de caractères et
non pas des noms de fichiers.

