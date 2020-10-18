#<center>Réseaux électrique</center>
##<center><span style="color:"black">Rapport de recherches</span></center>
######<center>Guillaume DESSERME, Nicolas PETIT, <span title="Le meilleur du groupe!">Louison SARLIN--MAGNUS</span>, Florian SIGALAS, Clément SIRJEAN</center>

<br>
<center>
  <figure>
    <img src="https://www.groupe-bage.com/images/metiers/reseau-electriques.jpg"
    width="600"
    >
    <figcaption>*Figure 1: Ligne Très Haute Tension (THT)*</figcaption>
  </figure>
</center>


<br>
<br>
<br>
<br>

***



####<a href="#def"><span style="color:black">1. Définition</span></a>
####<a href="#role"><span style="color:black">2. Rôles d'un réseau électrique</span></a>
####<a href="#architecture"><span style="color:black">3. Architecture</span></a>
#####<a href="#transport"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.1 Réseau de transport</span></a>
#####<a href="#distribution"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.2 Réseau de distribution</span></a>
####<a href="#stabilité"><span style="color:black">4. Stabilité du réseau</span></a>
####<a href="#black-out"><span style="color:black">5. Black-Out</span></a>
#####<a href="#black-def"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5.1 Définition</span></a>
#####<a href="#black-exemple"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5.2 Exemple de black-out</span></a>
####<a href="#bateau"><span style="color:black">6. Réseau électrique à bord des navires</span></a>
#####<a href="#bateau-config"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6.1 Configuration MN</span></a>
#####<a href="#bateau-sous"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6.2 Cas des sous-marins</span></a>
#####<a href="#bateau-conduite"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6.3 Le système de conduite centralisé</span></a>
####<a href="#smart-grids"><span style="color:black">7. Smart-Grids</span></a>
#####<a href="#smart-def"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;7.1 Définition des Smart Grids</span></a>
#####<a href="#smart-contraintes"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;7.2 Les contraintes du réseau électrique</span></a>
#####<a href="#smart-avantages"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;7.3 Les avantages pour le consommateur</span></a>
#####<a href="#smart-bilan"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;7.4 Bilan de l'utilisation des Smart-Grids</span></a>
####<a href="#voiture-electrique"><span style="color:black">8. Voiture électrique</span>
#####<a href="#voiture-politique"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.1 Une volonté politique</span>
#####<a href="#voiture-limites"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.2 Limites de la voiture électrique</span>
#####<a href="#voiture-impact"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.3 Impact sur les réseaux électriques</span>
#####<a href="#voiture-bilan"><span style="color:black">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.4 Quel futur pour la voiture électrique?</span>
####<a href="#sources"><span style="color:black">Sources</span>



<br>
<br>
<br>
<br>

***
###<a id="def"><span style="color:black">1.Définition</span></a>
Un réseau électrique est l'ensemble des infrastructures permettant d'acheminer l'énergie électrique des lieux de production jusqu'aux lieux de consommation.  
Ce réseau doit aussi assurer la gestion dynamique de l'ensemble production-transport-consommation, mettant en œuvre des réglages ayant pour but d'assurer la stabilité de l'ensemble. Il est constitué de lignes électriques et de postes de transformation. 

<center>
  <figure>
    <img src="https://img.aws.la-croix.com/2019/03/04/1201006339/Photo-dillustration-En-Allemagne-7-700-kilometres-cables-necessaires-1-750-seulement-effet-approuves-950-realises_0_729_487.jpg"
    width="600"
    >
    <figcaption>*Figure 2: Ligne Très Haute Tension (THT)*</figcaption>
  </figure>
</center>


<br>
<br>
<br>
<br>

***

###<a id="role"><span style="color:black">2. Rôles d'un réseau électrique</span></a>

Le rôle primaire du réseau électrique est d'acheminer de l'électricité a tous les français. Pour garantir cet accès on procède au calcul du "critère de défaillance unique". C’est-à-dire qu'on prévoit à tout moment une solution alternative en cas de défaillance d'une ligne de transport. 

Pour réussir sa tâche et garantir l'accès à l'électricité à tous le CNES (Centre National d'Exploitation du Système) fait face a 3 obstacles:

  - Il faut produire en temps réel ce qu'on consomme. En effet on ne sait pas stocker l'énergie produite en période de faible utilisation pour la réinjecter dans le réseau plus tard.
  - La consommation varie beaucoup. Elle dépend de nombre facteurs comme la température, la saison, l'ensoleillement, etc.
  - Il faut acheminer l'électricité, des zones de productions aux zones de consommation, via les lignes sans les surcharger

Rte met a disposition sur son site un outil, appelé [*eco2mix*](https://www.rte-france.com/fr/eco2mix/eco2mix) qui permet d'observer en temps réel plusieurs facteurs importants, comme la consommation et la production etc. le tout en temps quasi-réel (actualisé toutes les 15 minutes). 

<center>
  <figure>
    <img src="https://media.castorama.fr/is/image/Castorama/NPC_HT_1710_comprendre_installation_electrique_2?wid=720&fmt=png"
    width="600"
    >
    <figcaption>*Figure 3: Schéma d'un réseau électrique*</figcaption>
  </figure>
</center>

<br>
<br>
<br>
<br>

***

###<a id="architecture"><span style="color:black">3. Architecture</span></a>

####<a id="transport"><span style="color:black">3.1 Réseau de transport</span></a>

Le territoire français est parcouru par plus de $100 000 km$ de lignes électriques.  
Les lignes qui assurent les longs trajets sont des lignes appelées "Très Haute Tension" ou THT et possèdent une tension de $400 000V$. Ces lignes permettent de transporter une grande quantité d'énergie tout en limitant au maximum les pertes.

Puis au fur et à mesure que l'on se rapproche des lieux de consommation on va abaisser progressivement la tension à $225 000V$ puis $90 000V$ puis $63 000V$. Cette diminution progressive de la tension dans les lignes permet de répartir au mieux l'énergie tout en limitant au maximum les pertes.
Dans certains cas particuliers comme les grosses industries il est possible de livrer des moyennes voire hautes tension ($225kV$, $90kV$ ou $63kV$).

Une ligne aérienne est généralement composée de 3 câbles électriques (ou 6 si on a 2 lignes sur le même pylône). On note souvent la présence d'un câble supplémentaire, il s'agit du "câble de garde" qui protège les lignes de la foudre en étant placé au dessus.
En plus des $100 000 km$ de ligne aérienne, le réseau français dispose de près de $6 000 km$ de lignes enfouies (aussi appelées lignes souterraines).

<center>
  <figure>
    <img src="https://www.edf.fr/sites/default/files/mediatheque/2018/transport/energie-a-az_reseau-tht_2018.png"
    width="600"
    >
    <figcaption>*Figure 4: Carte du réseau THT français*</figcaption>
  </figure>
</center>

Le réseau de transport est dirigé au niveau national par le Centre National d'exploitation du Système (CNES). Ce centre est responsable de l'équilibre du système entre la production et la consommation ainsi que les échanges avec nos voisins Européens. Il s'occupe des "autoroutes de l'électricité" c’est-à-dire des lignes de $400 000V$.

On a ensuite 7 centres régionaux qui s'occupent localement des lignes de plus faible tension. Ces centres gèrent donc des "Régions" et sont subdivisés comme suit:

  - Région Sud-Est
  - Région Grand Est
  - Région Nord
  - Région Sud-Ouest
  - Région Parisienne et Normandie
  - Région Ouest
  - Région Rhône Alpes Auvergne

Ces centres régionaux veillent en temps réel à l'équilibre consommation-production électrique dans les zones concernées.

<br>
<br>

####<a id="distribution"><span style="color:black">3.2 Réseau de distribution</span></a>

L'interface entre le réseau de transport et le réseau de distribution se fait par pas moins de 2 200 postes de transformation qui ont pour but d'abaisser les Hautes Tensions (90kV, 20kV) en tension utilisables par le consommateur (220V dans le cas d'un particulier).

Le réseau de distribution est donc bien plus long. En effet, il mesure pas moins d'1,3 million de kilomètres.

<center>
  <figure>
    <img src="https://www.fournisseur-energie.com/wp-content/uploads/2017/06/.%C3%89lagage-pr%C3%A8s-des-lignes-%C3%A9lectriques.png"
    width="600"
    >
    <figcaption>*Figure 5: Différents types de lignes électriques*</figcaption>
  </figure>
</center>

Ce réseau n'est pas contrôlé par une unique entité, comme le réseau de transport, mais par près de 200 régies ou entreprises locales. On cite le plus souvent Enedis qui contrôle a lui seul $95\%$ du réseau de distribution, mais on peut aussi citer SER (Strasbourg Électricité Réseau) qui est une entreprise privée qui fournit de l'électricité à près de 540 000 clients. 
La Commission de Régulation de l’Énergie (CRE) régule les plus grands de ces gestionnaires de réseau de distribution.

Le développement de la production d’énergie décentralisée (éolien, photovoltaïque, etc.) et de nouveaux usages (autoproduction, électro-mobilité, etc.) modifient le rôle des réseaux de distribution qui deviennent collecteurs de l'énergie produite par les plus petites installations de production.


<center>
  <figure>
    <img src="https://www.comwatt.com/wp-content/uploads/2018/08/logement-durable-panneaux-photovoltaiques-energie-solaire-1024x612.jpg"
    width="600"
    >
    <figcaption>*Figure 6: Exploitation photovoltaïque*</figcaption>
  </figure>
</center>

<br>
<br>
<br>
<br>

***

###<a id="stabilité"><span style="color:black">4. Stabilité du réseau</span></a>  

Elle est caractérisée par les fluctuations de puissances transitées dans le réseau et se mesure par les variations dans le temps des tensions et fréquences associées.  

Il faut distinguer :

  - La stabilité en régime statique : le réseau a un comportement stable, c’est-à-dire que, soumis à de petites perturbations, il revient à son point de fonctionnement initial ceci avec d’éventuelles oscillations amorties jusqu’au retour à l’équilibre.
  - La stabilité en régime transitoire : lorsque l’on passe d’un état stable statique à un autre, suite à une perturbation durable voulue ou non, ce changement d’équilibre s’accompagne d’un régime variable oscillatoire amorti considéré comme acceptable eu égard à des fourchettes prédéfinies de $\Delta U$, $\Delta f$, $\Delta t$.
  - L’instabilité en régime transitoire est observée lorsque, suite à une perturbation importante, le régime oscillatoire est divergent . Il induit une perte d’alimentation ou un nouvel état stable inacceptable (ex : moteur qui « rampe »).
  - La stabilité en régime dynamique : le réseau est apte à éviter tout régime oscillatoire divergent et à revenir à un état stable acceptable. Ceci inclut l’intervention éventuelle des protections et automatismes divers fonction des perturbations envisagées.


Les études de stabilité dynamique consistent à :

  - envisager les principaux scénarios critiques tels que court-circuit, perte d’énergie mécanique, perte de source électrique, variation de charge, contraintes de process.
  - prédire le comportement du réseau face à ces perturbations.
  - préconiser les mesures à prendre en exploitation, telles que type de protection, réglage de relais, délestages, configurations… pour éviter les modes de fonctionnement indésirables.  

**Les machines asynchrones:**

Par leur présence majoritaire dans les réseaux industriels (jusqu’à 80 % de la puissance consommée dans certaines installations), les moteurs asynchrones ont un rôle prépondérant dans les phénomènes de stabilité.
La stabilité du moteur dépend des positions relatives des courbes de couple moteur et résistant. Si le moteur subit une coupure ou un fort creux de tension pendant quelques instants, il va ralentir et se retrouver à une vitesse réduite, par exemple 70% de la vitesse de synchronisme.
La solution est souvent l’utilisation d’un automate de délestage et relestage progressif des charges. La stabilité peut donc être gérée en minimisant l’appel de courant et donc la chute de tension.  

En résumé, les moteurs asynchrones sont des acteurs importants dans le cadre de la stabilité dynamique et peuvent rencontrer des difficultés de fonctionnement suite à un passage brusque sous tension réduite.

**Les machines synchrones:**  

Les machines synchrones sont fréquentes dans les réseaux industriels. Elles peuvent être installées pour les besoins suivants :  

  - récupération de l’énergie d’un processus exothermique ou cogénération
  - besoin d’une source électrique complémentaire pour:
    + contrat Effacement Jours de Pointe (EJP)
    + Secours
    + Pointes
  - compensation d’énergie réactive
Elles jouent un rôle prédominant dans les phénomènes de stabilité des réseaux.

**La stabilité statique:**  


<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/689414727109181477/699263067006959816/unknown.png"
    width="600"
    >
    <figcaption>*Figure 7: Représeantation d'une machine synchrone*</figcaption>
  </figure>
</center>

Avec :

  - R : résistance statorique
  - X : réactance directe statorique
  - E : f.e.m. statorique créée par l’enroulement d’excitation rotorique
  - U : tension aux bornes du stator en charge


<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/689414727109181477/699263451503132692/unknown.png"
    width="600"
    >
    <figcaption>*Figure 8: Diagramme vectoriel d'une machine synchrone*</figcaption>
  </figure>
</center>

L’angle interne $\delta$ de la machine est défini comme l’angle entre les vecteurs $\vec{U}$ et $\vec{U}$.   
Cet angle est égal à celui dont le rotor est décalé par rapport à sa position de fonctionnement à vide (si $I = 0$, $\delta = 0$). En négligeant R, un calcul rapide montre que la puissance électrique active transmise au réseau se calcule par : $P = \frac{E.U.\sin{\delta}}{X}$  

Il est clair que la puissance électrique transmise au réseau est limitée à la valeur de : $\frac{E.U}{X}$ , valeur qui est atteinte pour $\delta = 90°$

**La stabilité dynamique :**  

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/689414727109181477/699265689701056522/unknown.png"
    width="600"
    >
    <figcaption>*Figure 9*</figcaption>
  </figure>
</center>

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/689414727109181477/699265484503253022/unknown.png"
    width="600"
    >
    <figcaption>*Figure 10*</figcaption>
  </figure>
</center>

$P_{active}=\frac{E.U_{charge}}{X_{total}}.\sin{\delta}$

Avec:
$X_{total} = X_{generateur} + X_{transformateur} + X_{ligne}$

    
Les problèmes de stabilité dynamique résultent du passage de la machine d’un état stable à un autre.
En conséquence, l’angle interne maximal $\delta_{max}$, peut être supérieur à 90 ° de façon transitoire. La limite de stabilité dynamique est donc plus élevée que la limite de stabilité statique.

Ainsi il en découle deux remarques importantes :

  - les risques de pertes de stabilité dynamique sont liés à des changements d’états importants et brusques du réseau ou de la turbine
  - les risques de pertes de stabilité dynamique sont d’autant plus importants que la puissance fournie par la machine synchrone est proche de la limite de stabilité statique.

**Les conséquences :**  

Connaissant le temps d'élimination du défaut, il est possible de connaître l'angle interne maximal en opération pour éviter le risque de sur-vitesse en cas de court-circuit pour le générateur. 
On le note : $\delta_{max,total}$  
Il est lié à l'impédance $X_{total}$, qu'on peut décomposer en plusieurs parties.  

On peut donc de même décomposer l'angle en fonction de ses causes :  
$\delta_{total} = \delta_{generateur} + \delta_{transformateur} + \delta_{ligne}$  


Le premier étant connu, le dernier est appelé angle de transport, il augmente avec la longueur de la ligne.
On a donc : $\delta_{max,generateur} = \delta_{max,total} - \delta_{transformateur} - \alpha$ , avec $\alpha$ l'angle de transport.


Plus la ligne est longue, plus l'angle interne du générateur doit être faible, la marge de manœuvre est réduite. Si ce critère n'est pas respecté, il y a un risque en cas de défaut que le générateur perde son synchronisme. Autrement dit que la centrale électrique cesse d'alimenter le réseau.

<br>
<br>
<br>
<br>

***


###<a id="black-out"><span style="color:black">5. Black-Out</span></a>
####<a id="black-def"><span style="color:black">5.1 Définition</span></a>  

Un black-out est un effondrement de la totalité du réseau électrique qui peut être la conséquence d’une pénurie s’étant aggravée ou d'un problème technique imprévu.  

En cas de pénurie d'électricité, nous pouvons habituellement compter sur les pays voisins, qui peuvent envoyer une partie de leur surproduction vers notre réseau mais ce n'est pas toujours possible.  

À ce moment-là, il se peut donc que la demande d'électricité dépasse l'offre. On parle alors d'un déséquilibre entre production et consommation qui provoque une baisse de la fréquence nominal.  
Ce déséquilibre est dangereux, car il pourrait entraîner l'effondrement du réseau d'électricité voir même créer une réaction en chaîne pouvant entraîner un black-out sur l'Europe.   

Pour éviter le black-out, on pratique délestage. 
Cette réduction partielle et intentionnelle de la consommation d'électricité devrait alors permettre aux centrales électriques de rétablir l'équilibre.  

####<a id="black-exemple"><span style="color:black">5.2 Exemple de black-out</span></a>  

Fin décembre 1999, deux tempêtes exceptionnelles par leurs intensités frappent de plein fouet l'Europe, en particulier la France, où pas moins de 3,6 millions de personnes se retrouvent sans courant.  

Paris échappe de peu au black-out, grâce aux équipes d'EDF qui limitent les dégâts sur le réseau électrique français. Cependant, la violence des tempêtes met à terre pas moins de 23 000 poteaux électriques et pylônes à haute tension, et provoque l'arrêt de 3 centrales nucléaires, dont celle de Braud-et-Saint-Louis, près de Blaye, en Gironde qui est partiellement inondée.  
À certains endroits, il faut 19 jours pour rétablir le réseau. Au vu de l'étendue des dégâts et des dommages causés, c'est la pire destruction qu'ait subi le réseau électrique français depuis sa création. 

<center>
  <figure>
    <img src="https://www.power-technology.com/wp-content/uploads/image-digitalinsightresearch/Archive/nri/power/features/Worst%20blackouts%20in%20the%20last%2050%20years/5-image.jpg"
    width="600"
    >
    <figcaption>*Figure x2: Conséquence d'un black-out aux États-unis*</figcaption>
  </figure>
</center>

<br>
<br>
<br>
<br>

***


###<a id="bateau"><span style="color:black">6. Réseau électrique à bord des navires</span></a>  

Les navires sont des gros consommateurs d'énergies, les besoins en énergies sont pour essentiellement:

- Les équipements servant à la manœuvrabilité.
- Les circuits de commandes et de surveillance.
- Les installations de sécurité.
- Les systèmes de vie à bord.
- Les équipements spécifiques.

Puissance navire de 150 mètre entre $5000$ et $10000 KW$
Tension du réseau classique d'un navire militaire $440V$ et $230V$ à partir des années 2010, $115 V$ pour les navires d'anciennes génération.
Tension continue à $380V$ en plus pour les sous-marins.
Fréquence navire militaire à $60 Hz$.

Il y a environ $300 Km$ de câble dans un navire de 150 mètres.

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/695917872723263559/695984688908468254/unknown.png"
    width="600"
    >
    <figcaption>*Figure x3: Exemple de production-consommation d'énergie*</figcaption>
  </figure>
</center>

Pour l'ensemble des navires l'électricité est produite par des alternateurs, cependant la force mécanique permettant de faire tourner ces alternateur dépend du type de propulsion:  

- Moteur diesel accoupler à un arbre à l'alternateur.  
- Turbine à Gaz accoupler à un arbre à l'alternateur.  

Cette installation peut ou non être en lien avec la partie propulsion suivant les navires.
Plusieurs technologies de propulsion permettent différentes configuration électrique, à titre d'exemple la plupart des navires ne nécessitant pas un gros système de propulsion choisissent un moteur diesel relier à l'alternateur pour ensuite au travers d'un moteur électrique permette la rotation des hélices. Dans ce cas précis nous parlons de diesel alternateurs.


<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/695917872723263559/695984976843505694/unknown.png"
    width="600"
    >
    <figcaption>*Figure x4: Schéma de principe de production et stockage de l'électricité à bord d'un navire*</figcaption>
  </figure>
</center>

####<a id="bateau-config"><span style="color:black">6.1 Configuration MN</span></a>  

FREMM : La puissance électrique totale installée est de $8400 kw$ et constituée de 4 DA MTU série 4000 de $2.1 MW$ débitant du courant sous $6600 V$ / $60 Hz$ transformé en $440V/60Hz$ via des transformateurs HT/BT.

BPC navire tout électrique Puissance DIESEL installée ; 3 diesels principaux WÄRTSILA 16V32LNE de $6480 kw$ à $720 tr/mn$ + 1 diesel auxiliaire WÄRTSILA 18V200 de $3150 kw$ à $1200 tr/mn$ soit une puissance totale de $22590 kw$ Coté alternateur en courant de distribution HT ( $6600V$/$60Hz$) çà donne 3 alternateurs principaux de $6250 Kw$ et 1 alternateur auxiliaire de $3000 kw$ soit une puissance génératrice totale de $21750 kw$.

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/695917872723263559/695986371692724274/unknown.png"
    width="600"
    >
    <figcaption>*Figure x5: Réseau principal de distribution*</figcaption>
  </figure>
</center>

Le principe de fonctionnement du réseau Force (réseau principal) est le même sur les navires et sous-marins, un grand nombre de batteries permettent de prendre le relais en cas de panne à bord pour le réseau secouru. La différence ce joue aux niveau du dimensionnement du réseau secondaire en fonction du nombre d'équipements secourus.  

Le réseau secouru est en circuit alimenté en tension continu expliquer par l'utilisation de batteries en conserver l'énergie secours.


####<a id="bateau-sous"><span style="color:black">6.2 Cas des sous-marins</span></a>  

Il y a deux type de sous-marin, ceux dit à propulsion nucléaire et ceux dit à propulsion conventionnelle.
Dans le cas d'un sous-marins nucléaire l'énergie électrique principale est produite par l'alternateur produite à son tour par les générateurs vapeur. (même principe que les centrales à terre mais miniaturisé).  

Dans le cas du sous-marin à propulsion conventionnelle, l'énergie électrique principale est en continue fournit par les batteries, celles-ci sont rechargés lors du démarrage du diesel alternateur.  

####<a id="bateau-conduite"><span style="color:black">6.3 Le système de conduite centralisé</span></a>  

Un power management système gère automatiquement toutes ces usines électriques en répartition de charge , couplage …etc . Le power management dit PMS porte un nom différent suivant le fabricant ou le type de navire, il peut aussi être appelé SMS (Ship Management System), le VMS (Vessel Management System), le SCCS ( Système de Conduite Centralisé et Supervision) etc...
Les navires de dernière génération sont gérés en réseau, l'ensemble de la boucle réseau permet au PMS de recevoir des données et transmettre des ordres, que ce soit automatiquement en fonction de la configuration et des données reçu ou manuellement par les opérateurs.

Exemple de sous-systèmes pris en charge par le PMS:

- Système d’acquisition et de traitement des données : mesures et alarmes, etc.
- Système de télécommande d’ensemble propulsifs : pas d’hélice, vitesse, etc…
- Gestion de la propulsion électrique : répartition, couplage, délestage, redémarrage des auxiliaires essentiels, démarrage automatique des diesels, etc.
- Contrôles, commandes automatique : pompes, vannes, télé-jaugeage, disjoncteurs, etc.

Le principe de fonctionnement d'un navire est relativement proche de la gestion du parc électrique légèrement plus moderne peut être.         



<br>
<br>
<br>
<br>

***


###<a id="smart-grids"><span style="color:black">7. Smart-Grids</span></a>   

####<a id="smart-def"><span style="color:black">7.1 Définition des Smart Grids</span></a>   

Dans l'optique de moderniser les réseaux électriques pour correspondre à l'évolution des consommations, des technologies de Smart grids (réseaux intelligents) sont déployées. Cela consiste à intégrer des nouvelles technologies de l'information et de la communication au réseau pour le rendre "intelligent", afin d'optimiser le transport et la production d'énergie en temps réel.  

Certaines contraintes seront mieux gérées grâce aux Smart grids telles que l'intermittence des énergies renouvelables et le développement de nouveaux usages comme le véhicule électrique.

<center>
  <figure>
    <img src="http://www.smartgrids-cre.fr/media/images/site_images/consommateurs/schema1.jpg"
    width="600"
    >
    <figcaption>*Figure x0: Projection d'évolution du nombre de véhicules légers électriques en France*</figcaption>
  </figure>
</center>

####<a id="smart-contraintes"><span style="color:black">7.2 Les contraintes du réseau électrique</span></a>  

Les nouvelles consommations:   

La climatisation, les appareils audio et vidéo ou le chauffage électrique se développent et accroissent la consommation.  
L’apparition de nouveaux usages de consommation, tels que la voiture électrique, amplifiera cette hausse. Face à cette augmentation prévisible, les réseaux électriques actuels ne seront plus suffisamment adaptés.  
$Pour éviter de renforcer les réseaux (coûteux), il sera nécessaire de contrôler les périodes de charge des véhicules électriques.

Les nouvelles énergies:  

Depuis quelques années, de plus en plus de sources d’électricité d’origine renouvelable sont reliées au réseau électrique.  

L’intermittence de cette production la rend très difficile à intégrer au réseau et ne correspond pas forcément aux périodes de consommation de pointe. L'électricité produite, ne pouvant être stockée, est alors perdue.  

Le développement des énergies de sources renouvelables est ainsi souvent freiné par une inadéquation des moyens de production avec le fonctionnement du réseau actuel.

<center>
  <figure>
    <img src="https://cdn.pixabay.com/photo/2016/03/29/17/23/solarpark-1288842_960_720.jpg"
    width="600"
    >
    <figcaption>*Figure x7: Parc de production éolien et solaire*</figcaption>
  </figure>
</center>

Les objectifs fixés par l'Union Européenne:  

- $20\%$ de la consommation énergétique totale proviendra des énergies de sources renouvelables ;
- à production équivalente de biens et de services en 2020 par rapport à 1990, l'Union européenne s'est fixé l'objectif de consommer $20\%$ d'énergies en moins ;
- réduction de $20\%$, voire de $30\%$ en cas d’accord international, des émissions de gaz à effet de serre par rapport à 1990.


Le réseau intelligent permettra d’intégrer les énergies renouvelables et de renseigner producteur, distributeur et consommateur sur l’utilisation de l’énergie.

####<a id="smart-avantages"><span style="color:black">7.3 Les avantages pour le consommateur</span></a>  

Les consommateurs vont devenir des acteurs de leur consommation, voire de la production grâce à leurs installations photovoltaïques et/ou d'éoliennes.  
  
Grâce aux compteurs intelligents, les consommateurs et les gestionnaires de réseaux connaîtront précisément la consommation d’un site ou d’un foyer. Les fournisseurs d’énergie pourront donc proposer aux consommateurs de nouvelles offres selon leur profil de consommation.  

En améliorant la connaissance sur la consommation électrique à l’aide de compteurs évolués, il sera plus facile d’éviter les pics de consommation et les pannes dues à une surcharge. La consommation électrique sera gérée de manière intelligente. Par exemple, pendant les horaires où la consommation est réduite, on pourra profiter de l’électricité produite pour charger sa voiture électrique.  

Le consommateur sera renseigné sur le meilleur horaire pour faire tourner une machine et il gérera alors de manière active sa consommation d'énergie.
Les pannes sur le réseau seront détectées beaucoup plus facilement et les opérations de maintenance, de relève et de conduite se feront à distance.  
Les centres de contrôle des gestionnaires des réseaux d’électricité seront également informés en temps réel des besoins en énergie des consommateurs : ils distribueront alors la juste quantité d’électricité sur le réseau.  

En résumé, les réseaux électriques intelligents permettront au consommateur d’avoir :
- une maison plus intelligente,
- des factures plus précises,
- des pannes mieux détectées et plus rapidement réparées,
- des offres tarifaires plus diversifiées.


####<a id="smart-bilan"><span style="color:black">7.4 Bilan de l'utilisation des Smart-Grids</span></a>  

En résumé, les réseaux électriques intelligents :

- faciliteront l’intégration de la production de sources renouvelables et décentralisée,
- rendront actif le consommateur au sein du système électrique,
- fourniront au consommateur la connaissance suffisante permettant un pilotage efficace de sa consommation,
- participeront à l’élaboration d’un système électrique décarboné.


<br>
<br>
<br>
<br>

***


###<a id="voiture-electrique"><span style="color:black">8. Voiture électrique</span></a>
**Préambule :**  
Le secteur des transports émet aujourd'hui environ un tiers des gaz à effet de serre.
La voiture électrique apparaît comme étant une solution pour atteindre la neutralité carbone d'ici 2050.  Et pourtant, des voix s’élèvent pour dénoncer les fausses promesses de ces véhicules qui ne seraient pas si écologiques.

**Quelques chiffres :**  
Le marché des véhicules électriques représente encore que $2,5\%$ des ventes d’automobiles dans le monde en 2019 ($2\%$ en France, $5\%$ en Chine, $50\%$ en Norvège) mais connaît néanmoins une forte progression : En 2018, les ventes ont bondi de plus de $60\%$ (2 millions de véhicules vendus) par rapport à l’année précédente.

####<a id="voiture-politique"><span style="color:black">8.1 Une volonté politique</span></a>  

La France a pour objectif de vendre $35\%$ de véhicules électriques d'ici 2030 et le gouvernement a annoncé dans le plan climat l'arrêt de la vente des véhicules thermiques et donc émetteurs de gaz à effet de serre à l'horizon 2040.  
Les constructeurs ont dès aujourd'hui des objectifs de restriction d'émission de CO2 qui les forcent à mettre sur le marché des voitures électriques, cependant l'offre de ces véhicules reste encore limitée.  
Aujourd'hui, les voitures électriques sont essentiellement fabriquées en Chine, qui détient plus de $50\%$ du marché (plus d'un million de vente). En Europe, les constructeurs ont du retard car la vente de la voiture électrique leur revient plus chère.
De plus, l'Europe, qui a actuellement un leadership mondial sur les véhicules thermiques, deviendrait dépendante de la Chine puisque $80\%$ du cobalt nécessaire à la construction des batteries lithium-ion proviennent de Chine, et cela représenterai près de **12 millions d'emplois** qui pourraient être menacés.  
En France, la loi des mobilités pourrait apporter certains avantages :

  - Stationnement gratuit (comme c'est déjà le cas à Oslo en Norvège par exemple).
  - Zones à mobilité restreintes où ces véhicules pourront évoluer sans problème.
  - Faire en sorte que tout soit très clair et simple pour l'utilisateur du véhicule électrique.

<br>
<br>

####<a id="voiture-limites"><span style="color:black">8.2 Limites de la voiture électrique</span></a>  

La fabrication est globalement plus polluante et plus émettrice de carbone, notamment pour la fabrication des batteries lithium-ion dont le recyclage est complexe et coûteux, et dont la fabrication nécessite environ $400 kWh$ d'énergie pour $1 kWh$ de stockage.  

Si on veut améliorer l'autonomie de la voiture, on doit augmenter le nombre/la taille des batteries, ce qui consomme d'autant plus d'énergie.  
Enfin, selon certaines études, la voiture électrique devient moins émettrice de CO2 que la voiture thermique à partir de $50.000 km$, or la voiture électrique n'est aujourd'hui pas en mesure et pas conçue pour effectuer de longues distances.  

Actuellement, aucune étude fiable démontre que le véhicule électrique réduira les émissions carbones, au contraire il pourrait exister un effet pervers selon les endroits où les batteries sont fabriquées.

<br>
<br>

####<a id="voiture-impact"><span style="color:black">8.3 Impact sur les réseaux électriques</span></a>  

Le déploiement d'infrastructures de charge de véhicules électriques sur l'ensemble du territoire est une condition sine qua non  du décollage des ventes de véhicules électriques.

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/695917872723263559/695969420492668998/unknown.png"
    width="600"
    >
    <figcaption>*Figure x6: Schéma décrivant le principe de Smart-Grid*</figcaption>
  </figure>
</center>

Ces infrastructures de recharge sont raccordées aux réseaux électriques. Elles auront donc un impact sur la gestion et la configuration du réseau aux échelons local, départemental et national.  

Une modélisation de la charge a été réalisée par les gestionnaires de réseaux à partir des statistiques d’usage des véhicules électriques, du type de recharge des batteries (lent, semi-rapide, rapide) et des caractéristiques des véhicules (capacité de la batterie, autonomie, technologie VHR (hybrides) versus VEB($100\%$ électrique)).  

Cette modélisation permet de définir des courbes de charge « naturelle » des véhicules électriques, sans gestion particulière de la recharge. Elles indiquent très nettement que le nouvel usage du véhicule électrique vient s’ajouter aux autres usages, souvent pendant les heures de forte consommation, et induit un accroissement notable de la consommation électrique à la pointe.  

<center>
  <figure>
    <img src="https://cdn.discordapp.com/attachments/695917872723263559/695970587163492362/unknown.png"
    width="600"
    >
    <figcaption>*Figure x1: Courbes de charge type pour un jour ouvré moyen pour  un million de véhicules électriques*</figcaption>
  </figure>
</center>

L’appel de puissance lié à la recharge des véhicules électriques pourrait donc avoir des conséquences économiques (renforcements du réseau) et des conséquences environnementales (recharge en période de pointe et donc émissions de CO2) potentiellement très importantes.

**Une autre question se pose : La France peut-elle alimenter l'ensemble de sa population en voiture électrique ?**


[Selon un rapport de RTE](https://www.rte-france.com/sites/default/files/rte_-_mobilite_electrique_-_principaux_resultats_-_vf.pdf) paru en 2019 et réalisé avec l’association AVERE France, d’ici 2035, notre système serait en mesure d’absorber un parc routier composé à $40\%$ de véhicules électriques.

Selon ce même rapport, un parc national composé de 15,6 millions de véhicules branchés (Estimation d'ici 2035, cf. Figue x.) représenterait une consommation de $35$ à $40 TWh$, soit $8\%$ de la production électrique totale française.

**La recharge pilotée, une opportunité pour le réseau électrique ?**  

L’électrification est même considérée comme une « opportunité », à condition que la recharge soit pilotée. Les millions de véhicules électriques branchés pendant plusieurs heures pourront en effet contribuer à terme à l’équilibre du réseau grâce au "*Véhicule to Grid*" (V2G), en y injectant du courant lors des pics de consommation.  

Une solution d’autant plus pertinente qu’une voiture est utilisée pour se déplacer seulement $4\%$ de son temps ! Sans attendre la mise en place du V2G, un pilotage simple tel qu’un système de lancement de charge en heures creuses similaire à celui de nos ballons d’eau chaude permettrait déjà d’éviter de forts appels de puissance et une économie de 5 millions de tonnes de CO2, estime RTE.





<br>
<br>

####<a id="voiture-bilan"><span style="color:black">8.4 Quel futur pour la voiture électrique?</span></a>  

Aujourd'hui, il est sûr que la voiture électrique ne constitue pas une solution de masse. Bien que l’utilisation de  l’énergie électrique soit plus propre que celle de l’essence, les systèmes d’exploitation pour fournir de l’électricité ne sont pas encore tous sans émettre de CO2. L’équation entre l'émergence des véhicules électriques, facteur de l’efficacité énergétique, et l'intégration des énergies de sources renouvelables est encore à résoudre, afin d’éviter d’utiliser les centrales thermiques pour compenser les pics de consommation engendrés par un rechargement simultané des véhicules électriques.

De plus, rendre le réseau intelligent et communicant, en développant les Smart Grids, est l’ambition de toutes les entreprises concernées par la voiture électrique, comme les fournisseurs d’électricité, les concepteurs des bornes électriques et les constructeurs automobiles.

Cependant, le *Shift-Project* et les ingénieurs spécialisés dans ce domaine nous rappelle qu'il est essentiel de nous réorienter vers des modes de vie plus sobres : Il est plus simple de s'affranchir d'un certain nombre de contraintes géopolitiques ou de balances commerciales en consommant moins et en fabricant des voitures certes peut-être moins confortables mais plus petites, sans oublier les transports en commun ou les vélos.





<br>
<br>
<br>
<br>


***

###<a id="sources"><span style="color:black">Sources</span></a>

Données sur le réseau de transport: [*EDF*](https://www.edf.fr/groupe-edf/espaces-dedies/l-energie-de-a-a-z/tout-sur-l-energie/l-acheminement-de-l-electricite/le-reseau-de-transport)  
Outil de visualisation de données en direct: [*eco2mix*](https://www.rte-france.com/fr/eco2mix/eco2mix)  
SER: [Strasbourg Électricité Réseaux](https://www.strasbourg-electricite-reseaux.fr/)  
Informations et détails sur les réseaux électriques français: [*CRE*](https://www.cre.fr/Electricite/Reseaux-d-electricite/Presentation-des-reseaux-d-electricite)  
Rapport de mobilité de Rte: [*Rte*](https://www.rte-france.com/sites/default/files/rte_-_mobilite_electrique_-_principaux_resultats_-_vf.pdf)  
Émission "Entendez-vous l'éco ?": [*France Culture*](https://www.franceculture.fr/emissions/entendez-vous-leco)  
Shift Project: [Shift Project](https://theshiftproject.org/en/home/)  
Données et graphiques: [Wikipédia](https://en.wikipedia.org/wiki/Main_Page)
Fonctionnement et utilité des Smart-Grids: [*CRE*](http://www.smartgrids-cre.fr/index.php?p=comprendre-les-smart-grids)  
