#<center>RESEAU</center>

##Chapitre 1: Je sais pas
Le code MANCHESTER !! YES !!
*c'est tout ce que j'ai retenu....*


##Chapitre 2: Fast Ethernet

Pour les utilisateur un reseau est un ensemble de machine, de cable et de boitier RJ45.

En réalité dans un entreprise il y a plusieurs réseau.

####Topologie réseau

On a le:
- **bus** : On est tous sur un câble coa0ial
- **étoile**: dérivé du bus
- **anneau**: intéressante

Plusieurs médias:

- En filaire: 
   + cuivre torsadé (on s'en fout que ça soit torsadé!! 5 minutes sur ça pour rien...), blindé ou non, avec des catégories évoluantes avec la vitesse et la qualité du câble.
   + fibre optique, mono-mode ou multi-mode

Les réseau0:

- Déterminisme: chacun son temps de parole. Le signal ne sera jamais brouiller car on parle que quand personne parle. Nuance il faut attendre que la parole me revienne.
    + Avantages: Pas de superposition de message
    + Inconvénient: Attendre que la parole revienne

- A compétition: Tu parle quand tu veu0. Si personne ne parle je parle, le risque de parler en même temps est faible.
    + Avantages: Rapidité
    + Inconvénient: Bruit


Pour le système déterministe on a un *jeton* qui tourne entre les machines. On peut configurer un priorité.

##Chapitre 3: Protocole TCP/IP

Pouvoir communiquer a un ordinateur peut importe le chemin

On ne garanti pas que l'info arrive de l'autre coté et dans l'ordre du coté IP.

Il faudra donc avoir des mécanismes qui s’affranchisse des problèmes ci-dessus.

On parle de data-gramme IP.

On a un adressage uniforme de 4 octet pour IPv4.

Son but a été aussi de masquer la nature physique des réseau0 qu'on emprunte.

Quand je vais envoyer un paquet la machine doit mettre en œuvre le phénomène de routage.

Sur les 3 premiers octets (premier, 2 premiers ou 3 premiers) de l'adresse IP on identifie le réseau.
Sur les 3 derniers octets (premier, 2 premiers ou 3 premiers) de l'adresse IP on identifie la machine.

***
On divise en 4 sous réseau0

| 128 | 64 | 32 | 16 | 8  | 4  | 2  |  1 |
|:----|:---|:---|:---|:---|:---|:---|---:|
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |

| RESEAU   | Adresse IP    | Adresse de broadcast |
|:---------|:--------------|:--------------------:|
| Reseau 1 | 193.49.48.0   |     193.49.48.63     |
| Reseau 2 | 193.49.48.64  |    193.49.48.127     |
| Reseau 3 | 193.49.48.128 |    193.49.48.191     |
| Reseau 4 | 193.49.48.192 |    193.49.48.255     |

***

#TD-IP-2020.pdf Subnets IP page 8

***
##1)

On divise en 8 sous réseau0

| 128 | 64 | 32 | 16 | 8  | 4  | 2  |  1 |
|:----|:---|:---|:---|:---|:---|:---|---:|
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 0  | 1  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 1  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 1  | 0  | 0  | 0  | 0  |  0 |
| 1   | 1  | 1  | 0  | 0  | 0  | 0  |  0 |


| RESEAU   | Adresse IP       |     Masque      | Adresse de broadcast |
|:---------|:-----------------|:---------------:|:--------------------:|
| Reseau 0 | 193.49.48.0/27   | 255.255.255.224 |     193.49.48.31     |
| Reseau 1 | 193.49.48.32/27  | 255.255.255.224 |     193.49.48.63     |
| Reseau 2 | 193.49.48.64/27  | 255.255.255.224 |     193.49.48.95     |
| Reseau 3 | 193.49.48.96/27  | 255.255.255.224 |    193.49.48.127     |
| Reseau 4 | 193.49.48.128/27 | 255.255.255.224 |    193.49.48.159     |
| Reseau 5 | 193.49.48.160/27 | 255.255.255.224 |    193.49.48.191     |
| Reseau 6 | 193.49.48.192/27 | 255.255.255.224 |    193.49.48.223     |
| Reseau 7 | 193.49.48.224/27 | 255.255.255.224 |    193.49.48.255     |

***
##2)

| **RESEAU** | **MACHINE** | **ADRESSE**   |
|:-----------|------------:|:--------------|
| 1          |           A | 193.49.48.34  |
| 1          |           B | 193.49.48.35  |
| 1          |           C | 193.49.48.36  |
| 2          |           D | 193.49.48.66  |
| 2          |           E | 193.49.48.67  |
| 2          |           F | 193.49.48.68  |
| 5          |           G | 193.49.48.162 |
| 5          |           H | 193.49.48.163 |
| 7          |           I | 193.49.48.231 |
| 7          |           J | 193.49.48.236 |
| 0          |           K | 193.49.48.4   |
| 0          |           L | 193.49.48.17  |
| 0          |           M | 193.49.48.20  |

***
##3)

Routeur R1:  
193.49.48.33 sur le sous-reseau 1  
193.49.48.65 sur le sous-reseau 2  

Routeur R2:  
193.49.48.69 sur le sous-reseau 2  
193.49.48.165 sur le sous-reseau 5  

Routeur R3:  
193.49.48.70 sur le sous-reseau 2  
193.49.48.133 sur le sous-reseau 7  

Routeur R4:
193.49.48.1 sur le sous-reseau 0  
193.49.48.193 sur le sous-reseau 6  
193.49.48.225 sur le sous-reseau 7  

RMP:  
193.49.48.194 sur le sous-reseau 6  

***
##4)

<img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-9/p1080x2048/87055251_192330161974339_3312437550731231232_n.jpg?_nc_cat=101&_nc_sid=b96e70&_nc_ohc=fUS-hjzRLssAX8GsJjj&_nc_ht=scontent-cdt1-1.xx&_nc_tp=6&oh=3bf5f76f2427c6f219a16092dadeb0a4&oe=5E920DE6" alt="!! Image Not Found !!"/>


***
##5)


| **193.49.48.34/27** |               A |
|:--------------------|----------------:|
| 193.49.48.0/27      | 193.49.48.33/27 |
| 193.49.48.32/27     |          Direct |
| 193.49.48.64/27     | 193.49.48.33/27 |
| 193.49.48.160/27    | 193.49.48.33/27 |
| 193.49.48.224/27    | 193.49.48.33/27 |
| 193.49.48.0/24      |    193.49.48.33 |

| **193.49.48.34/27** | A alternatif |
|:--------------------|-------------:|
| 193.49.48.32/27     |       Direct |
| 193.49.48.0/24      | 193.49.48.33 |

| **193.49.48.35/27** |      B+Internet |
|:--------------------|----------------:|
| 193.49.48.32/27     |          Direct |
| Defaut              | 193.49.48.33/27 |

| **193.49.48.66/27** |               D |
|:--------------------|----------------:|
| 193.49.48.0/27      | 193.49.48.70/27 |
| 193.49.48.32/27     | 193.49.48.65/27 |
| 193.49.48.64/27     |          Direct |
| 193.49.48.160/27    | 193.49.48.69/27 |
| 193.49.48.224/27    | 193.49.48.70/27 |


| **193.49.48.66/27** |     D altenatif |
|:--------------------|----------------:|
| 193.49.48.32/27     | 193.49.48.65/27 |
| 193.49.48.64/27     |          Direct |
| 193.49.48.160/27    | 193.49.48.69/27 |
| 193.49.48.0/24      |    193.49.48.70 |


| **193.49.48.67/27** |      E+Internet |
|:--------------------|----------------:|
| 193.49.48.32/27/27  | 193.49.48.65/27 |
| 193.49.48.64/27/27  |          Direct |
| 193.49.48.160/27/27 | 193.49.48.69/27 |
| Defaut              | 193.49.48.70/27 |

| **193.49.48.17/27** |              L |
|:--------------------|---------------:|
| 193.49.48.0/27      |         Direct |
| 193.49.48.32/27     | 193.49.48.1/27 |
| 193.49.48.64/27     | 193.49.48.1/27 |
| 193.49.48.160/27    | 193.49.48.1/27 |
| 193.49.48.224/27    | 193.49.48.1/27 |

| **193.49.48.17/27** | L alternatif |
|:--------------------|-------------:|
| 193.49.48.0/27      |       Direct |
| 193.49.48.0/24      |  193.49.48.1 |

| **193.49.48.20/27** |     M+Internet |
|:--------------------|---------------:|
| 193.49.48.0/27      |         Direct |
| Defaut              | 193.49.48.1/27 |


**Faire une table de routage**:  
J'identifie tous les reseau et sous réseau que je voudrais atteindre
Ensuite j'optimise


***

192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
192.168.4.0/24

On peut simplifier les 4 adresses par 192.168.0.0/22

| 128 | 64 | 32 | 16 | 8  | 4  | 2  |  1 |
|:----|:---|:---|:---|:---|:---|:---|---:|
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  1 |
| 0   | 0  | 0  | 0  | 0  | 0  | 1  |  0 |
| 0   | 0  | 0  | 0  | 0  | 0  | 1  |  1 |

On remarque que les 6 permière colonnes sont identiques, on peut donc simplifier en enlevant les 2 bit (qui correspondent aux 2 dernières colonnes) au / (netid) qui suit l'adresse.

Liens utiles:

[sebastienadam](https://www.sebastienadam.be/ipcalculator/)