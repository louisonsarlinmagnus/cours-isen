#<center>Réseaux</center>

##Chapitre 1: Tips

#### Faire une table de routage
J'identifie tous les Réseaux et sous réseau que je voudrais atteindre
Ensuite j'optimise

####Simplifier une adresse

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

On remarque que les 6 premières colonnes sont identiques, on peut donc simplifier en enlevant les 2 bit (qui correspondent aux 2 dernières colonnes) au / (netid) qui suit l'adresse.


##Chapitre 2: Fast Ethernet

Pour les utilisateur un réseau est un ensemble de machine, de câble et de boîtier RJ45.

En réalité dans un entreprise il y a plusieurs réseau.

####Topologie réseau

On a le:
- **bus** : On est tous sur un câble coaxial
- **étoile**: dérivé du bus
- **anneau**: intéressante

Plusieurs médias:

- En filaire: 
   + cuivre torsadé (on s'en fout que ça soit torsadé!! 5 minutes sur ça pour rien...), blindé ou non, avec des catégories évoluantes avec la vitesse et la qualité du câble.
   + fibre optique, mono-mode ou multi-mode

Les réseaux:

- Déterminisme: chacun son temps de parole. Le signal ne sera jamais brouiller car on parle que quand personne parle. Nuance il faut attendre que la parole me revienne.
    + Avantages: Pas de superposition de message
    + Inconvénient: Attendre que la parole revienne

- A compétition: Tu parle quand tu veux. Si personne ne parle je parle, le risque de parler en même temps est faible.
    + Avantages: Rapidité
    + Inconvénient: Bruit


Pour le système déterministe on a un *jeton* qui tourne entre les machines. On peut configurer un priorité.

##Chapitre 3: Protocole TCP/IP

Pouvoir communiquer a un ordinateur peut importe le chemin

On ne garanti pas que l'info arrive de l'autre coté et dans l'ordre du coté IP.

Il faudra donc avoir des mécanismes qui s’affranchisse des problèmes ci-dessus.

On parle de data-gramme IP.

On a un adressage uniforme de 4 octet pour IPv4.

Son but a été aussi de masquer la nature physique des réseaux qu'on emprunte.

Quand je vais envoyer un paquet la machine doit mettre en œuvre le phénomène de routage.

Sur les 3 premiers octets (premier, 2 premiers ou 3 premiers) de l'adresse IP on identifie le réseau.
Sur les 3 derniers octets (premier, 2 premiers ou 3 premiers) de l'adresse IP on identifie la machine.

On divise en 4 sous réseaux

| 128 | 64 | 32 | 16 | 8  | 4  | 2  |  1 |
|:----|:---|:---|:---|:---|:---|:---|---:|
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |

| Réseaux   | Adresse IP    | Adresse de broadcast |
|:---------|:--------------|:--------------------:|
| Réseaux 1 | 193.49.48.0   |     193.49.48.63     |
| Réseaux 2 | 193.49.48.64  |    193.49.48.127     |
| Réseaux 3 | 193.49.48.128 |    193.49.48.191     |
| Réseaux 4 | 193.49.48.192 |    193.49.48.255     |


## Exercice

<font size="5">**Énoncé:**  
Un réseau de classe C 193.49.48 est divisé (« subnetté ») en 8 sous-réseaux nommés sous-réseau 0, sous-réseau 1, ..., sous-réseau 7.</font>  
<br>
<br>
<b><font size="4">1) Donner pour chaque sous-réseau, l’adresse IP correspondante, l’adresse de broadcast, ainsi que le masque de sous-réseau en notation décimale pointée et en notation CIDR (/XX).
Sur le sous-réseau 1, sont installées les machines A, B et C d’adresses respectives (hostid) 2, 3 et 4.  
Sur le sous-réseau 2, sont installées les machines D, E et F d’adresses respectives 2, 3 et 4.  
Sur le sous-réseau 5, sont installées les machines G et H d’adresses respectives 2, et 3.  
Sur le sous-réseau 7, sont installées les machines I et J d’adresses respectives 7, et 12.  
Sur le sous-réseau 0, sont installées les machines K, L et M d’adresses respectives 4, 17 et 20.  </font></b>

On divise en 8 sous réseau

| 128 | 64 | 32 | 16 | 8  | 4  | 2  |  1 |
|:----|:---|:---|:---|:---|:---|:---|---:|
| 0   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 0  | 1  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 0  | 0  | 0  | 0  | 0  |  0 |
| 0   | 1  | 1  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 0  | 0  | 0  | 0  | 0  |  0 |
| 1   | 0  | 1  | 0  | 0  | 0  | 0  |  0 |
| 1   | 1  | 1  | 0  | 0  | 0  | 0  |  0 |


| Réseaux   | Adresse IP       |     Masque      | Adresse de broadcast |
|:---------|:-----------------|:---------------:|:--------------------:|
| Réseau 0 | 193.49.48.0/27   | 255.255.255.224 |     193.49.48.31     |
| Réseau 1 | 193.49.48.32/27  | 255.255.255.224 |     193.49.48.63     |
| Réseau 2 | 193.49.48.64/27  | 255.255.255.224 |     193.49.48.95     |
| Réseau 3 | 193.49.48.96/27  | 255.255.255.224 |    193.49.48.127     |
| Réseau 4 | 193.49.48.128/27 | 255.255.255.224 |    193.49.48.159     |
| Réseau 5 | 193.49.48.160/27 | 255.255.255.224 |    193.49.48.191     |
| Réseau 6 | 193.49.48.192/27 | 255.255.255.224 |    193.49.48.223     |
| Réseau 7 | 193.49.48.224/27 | 255.255.255.224 |    193.49.48.255     |

***
<br>
<br>
<b><font size="4">2) Donner les adresses IP de toutes les machines en notation décimale pointée.  
  Un routeur R1 relie les sous-réseaux 1 et 2; l’adresse du routeur (partie hostid) sur chaque sous-réseau est 1.  
  Un routeur R2 relie les sous-réseaux 2 et 5; l’adresse du routeur est 5 sur chaque sous-réseau.  
  Un routeur R3 relie les sous-réseaux 2 et 7; l’adresse du routeur est 6 sur le sous réseau 2 et 9 sur le sous-réseau 7.  
  Un routeur R4 relie les sous-réseaux 0 et 7; l’adresse du routeur est 1 sur chaque sous-réseau.  
Le routeur R4 a également une interface vers un routeur multi-protocole IP/X25 (nommé RMP) permettant l’accès à Internet. Cette interface est le sous-réseau 6, l’adresse de R4 sur ce sous-réseau est 1, celle de RMP est 2.  </font></b>

| **Réseaux** | **MACHINE** | **ADRESSE**   |
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
<br>
<br>
<b><font size="4">3) Donner toutes les adresses IP des routeurs R1, R2, R3, R4 et RMP sur tous leurs interfaces.  </font></b>

Routeur R1:  
193.49.48.33 sur le sous-Réseaux 1  
193.49.48.65 sur le sous-Réseaux 2  

Routeur R2:  
193.49.48.69 sur le sous-Réseaux 2  
193.49.48.165 sur le sous-Réseaux 5  

Routeur R3:  
193.49.48.70 sur le sous-Réseaux 2  
193.49.48.133 sur le sous-Réseaux 7  

Routeur R4:
193.49.48.1 sur le sous-Réseaux 0  
193.49.48.193 sur le sous-Réseaux 6  
193.49.48.225 sur le sous-Réseaux 7  

RMP:  
193.49.48.194 sur le sous-Réseaux 6  

***
<br>
<br>
<b><font size="4">4) Donner une représentation schématique du réseau.  </font></b>

<img src="https://scontent-cdt1-1.xx.fbcdn.net/v/t1.15752-9/p1080x2048/87055251_192330161974339_3312437550731231232_n.jpg?_nc_cat=101&_nc_sid=b96e70&_nc_ohc=fUS-hjzRLssAX8GsJjj&_nc_ht=scontent-cdt1-1.xx&_nc_tp=6&oh=3bf5f76f2427c6f219a16092dadeb0a4&oe=5E920DE6" alt="!! Image Not Found !!"/>


***
<br>
<br>
<b><font size="4">5) Donner les interfaces ainsi que les tables de routage de chaque machine et chaque routeur (excepté RMP), sachant que toute machine du réseau peut accéder à toute autre machine du réseau et que seules les machines B, E, G, I et M ont accès à Internet.  </font></b>


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
| Défaut              | 193.49.48.33/27 |

| **193.49.48.66/27** |               D |
|:--------------------|----------------:|
| 193.49.48.0/27      | 193.49.48.70/27 |
| 193.49.48.32/27     | 193.49.48.65/27 |
| 193.49.48.64/27     |          Direct |
| 193.49.48.160/27    | 193.49.48.69/27 |
| 193.49.48.224/27    | 193.49.48.70/27 |


| **193.49.48.66/27** |     D alternatif |
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
| Défaut              | 193.49.48.70/27 |

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
| Défaut              | 193.49.48.1/27 |




Liens utiles:

[sebastienadam](https://www.sebastienadam.be/ipcalculator/)