#<center>CARTAPUS</center>
<font size="1"><center>Là on me voit, là on me voit plus, on me voit, on me vois plus, on me voit un peu, on me voit plus, on me voit</center></font>

##Introduction

La carte SIM va mourir dans les prochaines années, remplacé par un élément sécurisé intégrer dans les appareils.

Brevet de la carte a puce en 1974, première carte en 1979.

Une SmartCard c'est une carte en plastique avec un microP en plus.

Usages: Télécommunication, paiement, ID, etc

Avantages: 

- Difficile a contrefaire
- Solide
- Fiable
- Portable et mobile

On appelle ContactChip les cartes avec la puce visible
On appelle ContactlessChip les cartes avec la puce masquée

Il existe des cartes hybrides comme les cartes de crédit.

La carte contient:

- CPU: Unité centrale de traitement
- ROM: Mémoire Read Only
- EEPROM: Electrically Erasable Programmable Read Only Memory
- RAM: Mémoire d'accès aléatoire

Sous les contacts on a la puce de la carte qui emporte les mémoires, le microprocesseur, etc.



***
##Chapitre 1: Signaux

Le signal est définit par:

- VCC: 5v à 3V ou 1,8V  
- CLK: 1 à 5MHz  
- T=0 ou T=1 protocole d'échange de données  
- ATR: Réponse au Reset (Anwser to Reset)  
- PPS: Sélection du protocole et des paramètres  
- APDU (Application Protocol Data Unit):
    + Echange de commandes/données entre le terminal et ICC
    + Terminal comme maitre / Carte comme esclave

>Cold Reset: <img src="https://i.imgur.com/s669Fpt.png"/>  
>Warm Reset Cf p.20: <img src="https://i.imgur.com/oXm86xa.png"/>  

Maintenant qu'on arrive a repérer les différentes phases de communication avec la carte on se penche sur les etu:
><img src="https://i.imgur.com/BhT1Obk.png"/> 

etu: La durée nominale d'un "moment"

**1 etu = 372 clk** (*pour l'ATR*)

Un moment: le remps où un circuit éléctrique I/O a une valeur et juste après une autre valeur (qui peut etre la même).

Avant de transmettre un octet:
On met l'I/O a 0 pendant un etu
Puis la data sur 8 bit, donc 8 etu
Puis un etu de bit de parité
Puis au minimum 2 etu de pause

><img src="https://i.imgur.com/Jb7Bymi.png"/> 



ATR donne des information au terminal (mobile par exemple)

><img src="https://i.imgur.com/9PiBsqA.png"/> 

Dans la trame ATR, le premier bit "TS" nous donne la convention utilisé lors de la communication.

**TS** est l'octet qui définit la convention direct ou indirect pour les poids faible et fort (little indian, big indian).

**T0** est l'octet qui défini les octets qui suivrons, si T0=1101111, on aura TA1 TB1 TD1 et TA2 TB2 TC2 TD2

**TA1** comporte la fréquence de communication et le baud-rate  
**TB1** Voltage de L’EPROM  
**TC1** Le temps de pause entre 2 caractère  
**TD1** Indique la présence de TA2, TB2, TC2, etc.  

Si on a pas TA2 alors négociation de vitesse (ie on utilise PPS)

**TB2**, **TC2** etc, des données sur la carte (Voltage, fréquence, etc.)

**TCK** méthode de vérification de transmission de la trame (XOR)

Pour le PPS:
><img src="https://i.imgur.com/iGZiSik.png"/>

Exo:

<img src="https://i.imgur.com/7UGjkrb.png"/>

**WI** est l'octet qui est stocké sur TC2
**WT** est le waiting time : <img src="https://i.imgur.com/fNgwKaT.png" style="width:12  0px;height:35px;"/>

Un fois la négociation PPS fini on arrive a l'APDU et TPDU:
(Application Protocol Data Unit et Transport   Protocol Data Unit)

On a plusieurs cas possible de communication:

**Cas 1**: C'est juste un *ping*  
**Cas 2**: On attend de la donnée en retour  
**Cas 3**: On envoi de la donnée  
**Cas 4**: On envoi de la donnée et on en attend en retour  

<img src="https://i.imgur.com/OLFab2b.png"/>


***
##Chapitre 2: OS

<img src="https://i.imgur.com/97bMMJZ.png"/>




***
##Chapitre 3: Chip

><img src="https://i.imgur.com/WYTrscm.png"/>




***
##Chapitre 4: NFC

><img src="https://i.imgur.com/N0qaUdf.png"/>


><img src="https://i.imgur.com/xnlaGKn.png"/>

