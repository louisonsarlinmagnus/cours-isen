#<center>Linux Embarqué</center>
<font size="1"><center>*pouloulou*</center></font>

##Exercice 1 
Intérêt du transport de l'électricité à haute tension.
On cherche à quantifier les pertes Joule occasionnées lors du transport d’une puissance électrique de 100MW sur une distance de 100km en triphasé.
Le facteur de puissance de la ligne est de 0, 95.
  
**1. Déterminer le courant de ligne pour une tension de 400 kV puis 100 kV.**  
$P =\sqrt{3} \times U \times Ixcos(\varphi)$  
$I = \frac{P}{\sqrt{3} \times U \times cos(\varphi)}$  
  
Donc $I = 152 A$ (pour U=400kV)  
Donc $I = 607,7 A$ (pour U=100kV)  

**2. La densité de courant dans les câbles de transport d’électricité est J = 0,7A=mm2.**  
**Déterminer la section nécessaire des conducteurs pour un transport en 400 kV.**  
$S=\frac{I}{J}$  
donc  
$S=\frac{152}{0,72}=212 mm^2$

**3. Le matériau utilisé pour les câbles de transport est un alliage d’aluminium (préféré au cuivre pour sa légèreté et son coût). La résistivité de ce matériau est ρ = 26.10−3Ωmm2/m.**   
**Déterminer alors la résistance électrique de chaque ligne de transport.**  
$R = \frac{\rho.L}{S}$

$R=\frac{0,026 \times 100000]}{212} = 12,3 \Omega$


**4. Pour les 2 tensions envisagées, déterminer les pertes Joule en ligne.**  
**Calculer alors le rendement du transport d’électricité.**  
$Pj=3RI²$  

$Pj=3 \times 12,3 \times 152^2=852,5 kW$

$r = \frac{P-Pj}{P}$ 

$r=\frac{1.10^{8} - 852.10^{3}}{1.10^{8}}=0,991$

***

##Exercice 2 
<font size="5">Stabilité en fréquence du réseau électrique</font>  
Un turbo-alternateur de centrale nucléaire a les spécifications suivantes: 1140 MVA/27 kV.
Il délivre de l’énergie au réseau comme l’indique le schéma ci-après:
<center>
  <img src="https://i.imgur.com/zuwWxzH.png" width="300"/>
</center>

**1.  Quelle est la puissance mécanique développée sur l’arbre ?**  
$P = Couple.\Omega$

**2.  Dans  une  machine  synchrone,  quelle  est  la  relation  existant entre  fréquence  du  réseau électrique et vitesse de rotation mécanique ?**  
$f_{Reseauélec} = \frac{N.p}{60}$   
avec N en tr/min et p le nombre de paire de pôles

**3.  Appliquer le PFD sur l’arbre en rotation. Expliquer pourquoi un équilibre entre productionet consommation est indispensable pour obtenir un réseau électrique stable en fréquence**  

$J\frac{d\omega(t)}{dt} = C_m(t) + C_r(t)$

Avec Cr le couple résistif, correspondant a la consommation d'énergie sur le réseau.  
Avec Cm le couple produit par la turbine.  

Le réglage de la fréquence réseau se fait par le biais de la puissance active. 

***

<font size="5">Pas d'exercice 3...</font>

***

##Exercice 4
<font size="5">Stabilité en tension du réseau électrique - réglage de la puissance réactive</font>  
On cherche à dimensionner le gradin de condensateurs du schéma ci-dessous pour compensertotalement la puissance réactive de la charge. Il s’agit d’un réseau triphasé 230V/400V.  
**1.  Déterminer la valeur de C à mettre en place.**  
On sait que : 

- $V=230V$ 
- $f=50Hz$ 
- $W=2 \times pi \times f =314 rad \times s^-1$ 
- $Q=P \times tan(phi)$  

Alors on calcule la valeur de la charge principale : 
$Q_{charge}=40 .10^3 \times \tan{46} ~= 40.8kVAR$
Car : $\cos(\phi) = 0.7$ <=> $\phi=\arccos{0.7} ~= 46°$

Pour 1 condensateur (ici on va prendre un phi=-90°), on sait que
$P_{abs}=V \times I \times \cos(\phi)$

Or on sait que  $P_{abs} = 0W$ pour un condensateur. 

$P_{reac}=V \times I \times \sin(\phi)= V \times I \times sin(-90) = -V \times I W$ 

Or le module de $I$ est: $\mid I\mid = CwV$

Donc: $Q_{1 condensateur} = -V^2wC$ 

 Ainsi pour 3 condensateurs on obtient : $Q_{3 condensateur} = -3V^2wC$ 

 

Or on souhaite annuler toutes les puissances réactives cad :  
$Q_{3 condensateur} + Q_{charge} = 0$ 
$\iff$  $-3V^2wC +40.8 .10^3 = 0$ 
$\iff$  $C = Q_{charge}/3 \times V² \times w = \frac{ 40.8 .10^3}{3 \times 230² \times 2 \times pi \times 50}$  
$C = 0.8 mF$

**2.  Le distributeur d’électricité ne facturant l’énergie réactive qu’à partir d’un tan(φm a x)=0, 4,calculer la valeur de C qui suffirait.**  
Tout pareil qu'au dessus sauf qu'on souhaite annuler toutes les puissances réactives cad : 

$Q_{3condensateur} + Q_{charge} = Q_{total}$ 

$\iff$  $-3V²wC +40.8 .10^3 = 16 .10^3$ 

$\iff$  $-3V²wC = (16-40.8) .10^3$  

$\iff$  $C = \frac{(16-40.8) .10^3}{3 \times V² \times w} = \frac{24.8 .10^3}{3 \times 230² \times 2 \times pi \times 50}$  
Finalement : $C = 0.49mF$  

**3.  Le  déclenchement  de  nouvelles  charges  modifie  la  charge  :  $P=60  kW$  et  $\cos(φ)=0, 72$.Déterminer la nouvelle puissance réactive échangée avec le réseau sans modifier la valeurde C calculée à la question 2.**  
**Conclure.**  

Alors on commence par calculer la valeur de la charge principale :   
$Q_{charge}=60 .10^3 \times \tan(44) ~= 57.9kVAR$  
Car:  
$\cos(\phi) = 0.72 \iff \phi=\arccos(0.72) ~= 44°$ 
     
Pour 1 condensateur (ici on va prendre un $\phi=-90°$), on sait que : 
$P_{abs}=V \times I \times cos(phi)$

Or on sait que  $P_{abs} = 0W$ pour un condensateur. 
$P_{reac}=V \times I \times \sin(\phi)= V \times I \times \sin(-90) = -V \times I W$  

Or le module de I est: $\mid I\mid = CwV$  

Donc: $Q_{1condensateur} = -V²wC$ 

Ainsi pour 3 condensateurs on obtient : $Q_{3condensateur} = -3V^2wC$ 

Donc : 
$Q_{total} = Q_{3condensateur} + Q_{charge}$  
$\iff$  $-3V²wC +57.9 .10^3$  
$\iff$  $(-3 \times 230² \times 2 \times pi \times 50 \times 0.49 \times 10^-3) + 57.9 .10^3$ 
Finalement : $Q_{total} = 33.47kVAR$ 


<center>
  <img src="https://cdn.discordapp.com/attachments/695512780085919774/695594396476899328/unknown.png" width="600"/>
</center>

***

##Exercice 5
<font size="5">Stabilité en tension du réseau électrique</font>  
Le caractère inductif et résistif des lignes de transport électrique ont pour conséquence de faire chuter la tension du réseau. En vous basant sur le modèle monophasé de ligne proposé ci-dessous, nous allons déterminercette chute de tension.

<center>
  <img src="https://cdn.discordapp.com/attachments/695512780085919774/695594926343192676/unknown.png" width="600"/>
</center>

**1.  Exprimer les puissances active et réactive de la charge en fonction de la tension efficace $V_c$.**  
$Pa=V_c \times i \times cos(\varphi)$  
$Pr=V_c \times i \times sin(\varphi)$  

**2.  Tracer le diagramme de Fresnel ($V_c$,$V_p$,$\Delta V$ et $I$) du circuit en prenant la tension $V_c$commeréférence.**  

<center>
  <img src="https://cdn.discordapp.com/attachments/695917872723263559/695918177263157268/unknown.png" alt="Image not found" width="600"/>
</center>

Avec $Vp = R \times I+jLw \times I+Vc$

**3.  Si l’on suppose que la ligne n’est pas trop chargée, l’angle entre $V_c$ et $V_p$ peut être négligé.Déterminer alors l’expression de $\Delta V$ en fonction de$I$,$R$,$L$,$\omega$ et $\phi$.**  

<center>
  <img src="https://cdn.discordapp.com/attachments/695917872723263559/695918249086287983/unknown.png" alt="Image not found" width="600"/>
</center>

One voit que :  
$X = L \times \omega \times I \times \sin(\phi)$   
$Y = RI \times \cos(\phi)$  

Alors : $\Delta V = X+Y = (L \times \omega \times I \times \sin(\phi)) + (RI \times \cos(\phi))$

**4.  Exprimer alors la chute de tension $\Delta V$ en fonction de $P$ et $Q$.**  
$\Delta V = \frac{R*P+L*w*Q}{Vc}$  

**5.  Conclure.**  
Il faut ajouter des condensateurs pour compenser Q.
***

##Exercice 6
<font size="5">Stabilité en tension</font>  
Une  ligne  aérienne  triphasée  alimente  un  récepteur  triphasé  équilibré  qui  consomme  unepuissance active $P1$ de $1,50 MW$ et impose un facteur de puissance $k1$ de $0,9$.  
La valeur efficace de la tension entre phases à l’arrivée de la ligne est $U_A=20kV$, sa fréquence $f=50 Hz$.  
Chaque fil de ligneaune résistance linéique de $220mΩ/k$ met une inductance linéique de $1,2 mH/km$. La ligne fait $50km$ de long.  
Le but est de calculer la valeur efficace $U_D$ de la tension composée au départ de la ligne.  

**1.  Schématiser la situation.**  

<center>
  <img src="https://cdn.discordapp.com/attachments/695512733163978782/695914570933600366/exo6.JPG" width="600"/>
</center>

**2.  Déterminer la valeur efficace de l’intensité $I$ du courant dans un fil de ligne.**  
On sait que : 
$R =rl \times L=0.22 \times 50 .10^3=11000\Omega$ 
$P_1=(\sqrt{3}) \times Ua \times I \times cos(phi)=(\sqrt{3}) \times I \times 20 .10^3 \times 0.9$ 

Alors : 
$I=\frac{P_1}{\sqrt{3}} \times U_A(t) \times \cos(\phi)=\frac {1.5.10^6}{\sqrt{3} \times 20 .10^3 \times 0.9} =\frac {1.5 .10^6}{\sqrt{3} \times 20 \times 0.9}$  
Donc : $I=48A$  

**3.  Déterminer la puissance réactive $Q1$ absorbée par la charge.**  

On sait que :   
$\cos(\phi) =0.9  <=>  \phi=\arccos(0.9) ~=26°$   
$Q=\sqrt{3} \times Ua \times I \times \sin(\phi)$ 
Alors :   
$Q1= \sqrt{3} \times 20 .10^3 \times 48 \times sin(26)$   
Donc : $Q1 = 729kVAR$ 

**4.  Déterminer les puissance active $P2$ et réactive $Q2$ consommées par la ligne.**  

$R = R_{ligne}\times L=0.22. 10^-3\times 50.10^3=0.22\times 50=11\Omega$  
  
$L = L_{ligne} \times l =1.2.10^{-3}\times50.10^3=1.2\times50=60mH$  
  
$P_2 = P_{resistance} + P_{inductance}$  
$\Rightarrow$ $P_{inductance} = 0 VAR$ car $\cos(90)=0$  


$Q_2 = Q_{resitance} + Q_{inductance}$   
$\Rightarrow$ $Q_{resitance} = 0 VAR$ car $\sin(0) = 0$  
  
$P_2 = 3\times R\times I^2 = 3\times 11\times 48^2 ~= 76kVAR$  
$Q_2 = 3\times L\times \omega \times I^2 = 3\times 60.10^{-3}\times 2\times \pi\times 50\times 48^2 ~= 130.3kVAR$  

  
**5.  En déduire la valeur efficace de la tension entre phases au départ de la ligne $U_D$ ainsi que la chute de tension relative $\frac{\Delta U}{U_D}$**  

On applique le **théorème de Boucherot**:  
$P_T = \sum_{i=1}^{n} P_i$  et  $Q_T = \sum_{i=1}^{n} Q_i$  

$S_D=\sqrt {P_D^2+Q_D^2} = \sqrt{3}U_DI$  

$Q_D = Q_1 + Q_2 =(729+130.3).10^3 = 859.3kVAR$  
$P_D = P_1 +P_2 = 1.5.10^6 + 76.10^3 = 1576kW$  
$S_D = \sqrt {(1576.10^3)^2 +(859.3.10^3)^2} ~= 1.795MVA$  

Donc:  
$U_D =\frac{S_D}{\sqrt{3}.I} =\frac{1.795.10^6}{\sqrt{3}\times 48}=22kV$  
$\Delta(U) = (U_D-U_A) = 2kV$  
$\frac{\Delta U}{U_D} = \frac{2}{22} = 0.09 = 9\%$  

***

##Exercice 7
<font size="5">Nécessité d'interconnecter les centrales de production</font>  
###Partie A
<font size="3">Impact de la distance au site de production</font>
Nous prenons un modèle monophasé de ligne pour l’étude de la chute de tension dans leréseau électrique THT de tension composée $U_r=400kV$.
La ligne a une inductance linéique $l=1,1mH/km$. La distance en kms séparant centrale de production et récepteur est notée $x$. Lerécepteur est de type inductif et présente un facteur de puissance de $0,90$.

**1. Schématiser la situation.**  

<center>
  <img src="https://cdn.discordapp.com/attachments/695512733163978782/695930563336470538/exo7.JPG" width="600"/>
</center>


**2.A l’aide d’un diagramme de Fresnel, montrer que l’on peut approcher la tension simple disponible au niveau du récepteur par: $V_A=V_D−l.x.ω.I.\sin{\phi}$**  


<center>
  <img src="https://cdn.discordapp.com/attachments/695512733163978782/695935659868946432/unknown.png" width="600"/>
</center>

L'angle entre $V_A$ et $V_D$ est néglieable ==> $V_D$ devient l'homothétie de $V_A$  
  
**3.On donne $I=830 A$. Tracer alorsVAen fonction de $x$ pour une ligne allant jusqu’à 100 kms.**  

$\cos(\phi) =0.9 \iff \phi = \arccos(0.9) = 26°$  
$V_D = \frac{U_D}{\sqrt{3}} = 231kV$  

$V_A=V_D−l.x.ω.I.\sin{\phi} = (231.10^3)-(1.1\times 100\times 2\times \pi\times 50\times \sin(26)\times 830) = 218kV$


**4. Sur le réseau THT la tension composée ne doit pas descendre en dessous de $U_{min}=380kV$. A quelle distance cette contrainte n’est plus respectée?**  

$V_{min}= \frac{U_{min}}{\sqrt{3}} ~= 219kV$

$V_A = V_D-I.l.\omega.x.\sin(\phi)$
$\iff V_D-V_A = I.l.\omega.x.\sin(\phi)$
$x=\frac{V_D-V_A}{I.l.\omega.x.\sin(\phi)} = \frac{231-218}{830\times 1,1.10^{-3}\times 2\pi \times 50\times\sin(26)} =1034m$

###Partie B
<font size="3">Interconnexion des centrales de production</font>  
Nous allons voir comment un réseau de production maillé permet de limiter la chute de tensionen ligne.
Les 2 centrales sont espacées d’une distance $d=200kms$. Nous supposerons pour la suiteque les tensions de réseau aux deux extrémités de la ligne sont synchrones.


<center>
  <img src="https://cdn.discordapp.com/attachments/695512780085919774/695617315516973076/unknown.png
" width="600"/>
</center>


**1. DéterminerVAen fonction de la distance de lignex.**  

$\underline{U_{L1}} = \underline{U_{L2}}$  
$\iff \underline{I_1}.j.L_1\omega = \underline{I_1}.j.L_2\omega$  
$\iff \underline{I_1}.j.l.x\omega = \underline{I_1}.j.l.(d-x)\omega$  
Or:  
$\underline{I} = \underline{I_1} + \underline{I_2} \iff \underline{I_2} = \underline{I} - \underline{I_1}$  

Donc:  
$\underline{I_1}= \underline{I}.\frac{d-x}{d}$  

<img src="https://cdn.discordapp.com/attachments/695917872723263559/695981126451331142/unknown.png
" width="400"/>


**2. En prenant $I=830 A$ et $\cos{\phi}=0,9$, tracer la tension $V_A$ en fonction de $x$.**  

**3. Conclure.**  

***

##Exercice 8
<font size="5">Optimisation du réseau électrique</font>  
Pour le circuit suivant, sachant que les charges sont alimentées en 230V, déterminer :  

**1.  Le facteur de puissance des deux charges parallèles**  

**2.  L’amplitude du courant $I_s$, la puissance active perdue dans la ligne et la puissance apparentefournie par la source**  

**3.  Si la fréquence de la source est de $50Hz$, calculer la valeur du condensateur nécessaire auniveau de la charge pour corriger le facteur de puissance à 0.95. Recalculer les valeurs de laquestion 2.**  



<center>
  <img src="https://cdn.discordapp.com/attachments/695512780085919774/695617914862305330/unknown.png" width="600"/>
</center>

