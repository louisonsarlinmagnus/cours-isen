#<center>CARTAPUS</center>
######<center>Là on me voit, là on me voit plus, on me voit, on me vois plus, on me voit un peu, on me voit plus, on me voit</center>

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

>Cold Reset: <img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-9/89514407_565190654344465_9144123495037272064_n.png?_nc_cat=103&_nc_sid=b96e70&_nc_ohc=pdo4sw9IZL4AX8c8Tgc&_nc_ht=scontent-cdt1-1.xx&oh=fb9519d24017651f7444bfbfe69ef3ac&oe=5E915778"/>  
>Warm Reset Cf p.20: <img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-9/89057693_204625250623129_7449825305549602816_n.png?_nc_cat=101&_nc_sid=b96e70&_nc_ohc=lyg2K6ON1YwAX-WgxNe&_nc_ht=scontent-cdt1-1.xx&oh=d8742bd2bdfce7a1161e071ebeac9352&oe=5E8F846C"/>  

><img src="https://yncrea.sharepoint.com/sites/ITIIP16TL/Documents%20partages/SMARTCARD/Exo1.JPG"/>

Maintenant qu'on arrive a repérer les différentes phases de communication avec la carte on se penche sur les etu:
><img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89437580_201785884427453_4924412285285302272_n.png?_nc_cat=105&_nc_sid=b96e70&_nc_ohc=Wfzrw7TXrBEAX8-HTPN&_nc_ht=scontent-cdt1-1.xx&oh=d14f6a88deafe802f3f123abd80ff417&oe=5EA3D571"/> 

etu: La durée nominale d'un "moment"

**1 etu = 372 clk** (*pour l'ATR*)

Un moment: le remps où un circuit éléctrique I/O a une valeur et juste après une autre valeur (qui peut etre la même).

Avant de transmettre un octet:
On met l'I/O a 0 pendant un etu
Puis la data sur 8 bit, donc 8 etu
Puis un etu de bit de parité
Puis au minimum 2 etu de pause

><img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89473476_2853454071390961_7269321724317925376_n.png?_nc_cat=105&_nc_sid=b96e70&_nc_ohc=OAUQFF7lZdcAX9mN-3w&_nc_ht=scontent-cdt1-1.xx&oh=750f69b5c15188f2dcca6601a2af33a6&oe=5E9410B0"/> 



ATR donne des information au terminal (mobile par exemple)

><img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89448133_663325001146637_834956481454407680_n.png?_nc_cat=104&_nc_sid=b96e70&_nc_ohc=pcwC6M5dl5gAX_h0FMq&_nc_ht=scontent-cdg2-1.xx&oh=d8e671ddb320c39009373ca3923dfbbd&oe=5E8DC60A"/> 

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
><img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89471208_1079941689005027_8495667146548838400_n.png?_nc_cat=105&_nc_sid=b96e70&_nc_ohc=MVN0_Wsq53QAX-g9xRr&_nc_ht=scontent-cdt1-1.xx&oh=96bc0a633338f6a4f1f583ad4174f1b9&oe=5EA3995A"/>

><img src="https://yncrea.sharepoint.com/sites/ITIIP16TL/Documents%20partages/SMARTCARD/exo2,1.JPG"/>

Exo:

<img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89070147_2443645919279265_7364514022256803840_n.png?_nc_cat=104&_nc_sid=b96e70&_nc_ohc=8MzMr4rPctsAX_VhKhQ&_nc_ht=scontent-cdg2-1.xx&oh=8e10618780bc74247c31d7a13236e05c&oe=5E973317"/>

**WI** est l'octet qui est stocké sur TC2
**WT** est le waiting time : <img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-9/89124307_303887257254383_935953861485527040_n.png?_nc_cat=110&_nc_sid=b96e70&_nc_ohc=LhIvHjIqxMUAX93B5EN&_nc_ht=scontent-cdg2-1.xx&oh=f923b37208c38e19feaedc032992e4d2&oe=5E9242AE" style="width:12  0px;height:35px;"/>

Un fois la négociation PPS fini on arrive a l'APDU et TPDU:
(Application Protocol Data Unit et Transport   Protocol Data Unit)

On a plusieurs cas possible de communication:

**Cas 1**: C'est juste un *ping*  
**Cas 2**: On attend de la donnée en retour  
**Cas 3**: On envoi de la donnée  
**Cas 4**: On envoi de la donnée et on en attend en retour  

<img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-9/89437573_697025617787865_554203905358036992_n.png?_nc_cat=102&_nc_sid=b96e70&_nc_ohc=Dx0IPdxKX4oAX9T3ulN&_nc_ht=scontent-cdg2-1.xx&oh=f05e8e2a72ba8ca5b505c580754464b9&oe=5E90D72E"/>


***
##Chapitre 2: OS

<img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89345169_191217678831513_4835345899200708608_n.png?_nc_cat=107&_nc_sid=b96e70&_nc_ohc=bK-BL6igN64AX-G9PLx&_nc_ht=scontent-cdg2-1.xx&oh=1e28c3b8ec1062f905dc30a001d6d378&oe=5E8FC7DE"/>




***
##Chapitre 3: Chip

><img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89506309_1047274955655253_1121869780114997248_n.png?_nc_cat=105&_nc_sid=b96e70&_nc_ohc=JTCpi-ETMLEAX-Y9gcP&_nc_ht=scontent-cdt1-1.xx&oh=9d78b99236ca60906c2975e1b125e0ec&oe=5E927007"/>

><img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-0/p480x480/88959449_211379366938355_7808441833381429248_n.png?_nc_cat=101&_nc_sid=b96e70&_nc_ohc=qRYqJw3wbycAX8MiWQl&_nc_ht=scontent-cdt1-1.xx&oh=9c480cec981594ee9363b541bcfc6acd&oe=5E9271E9"/>




***
##Chapitre 4: NFC

><img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-0/p480x480/88987149_3820814784625744_1423936290331557888_n.png?_nc_cat=100&_nc_sid=b96e70&_nc_ohc=GYwDY4-bMgoAX9JxRJj&_nc_ht=scontent-cdg2-1.xx&oh=5df248bf2244d83c7dfe270663d020d9&oe=5E9026AC"/>


><img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.15752-0/p480x480/89269857_195551791777361_2940133949969530880_n.png?_nc_cat=100&_nc_sid=b96e70&_nc_ohc=kfsd8SnGoHsAX_Hcydf&_nc_ht=scontent-cdg2-1.xx&oh=b4f8cf467e2287f2f3ebf90266717202&oe=5EA1F915"/>





***
##Chapitre 5: Java Card




