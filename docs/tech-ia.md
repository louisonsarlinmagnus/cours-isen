# <center>Intelligence Artificielle</center>

## Préliminaires

Objectifs:

- Définir ce qu'est une intelligence (artificielle)
- Découvrir plusieurs pans de l'IA
- Apprendre quand utiliser ces algorithmes et comment les personnaliser
- Utiliser ces connaissances pour optimiser la performance et/ou la consommation de ressources => efficacité


[Contact mail](ghislain.oudinet@yncrea.fr)

[Lien vers le cours](https://educ.isen-mediterranee.fr/cours/my/)

Objectifs:

- Définir ce qu'est une intelligence (artificielle)
- Découvrir plusieurs pans de l'IA
- Apprendre quand utiliser ces algorithmes et comment les personnaliser
- Utiliser ces connaissances pour optimiser la performance et/ou la consommation de ressources => efficacité


Dans ce cours nous aborderons uniquement les pistes de départ de cette matière. Il faudrait des semaines de cours pour aborder plus solidement cette matière.

Rendre le travail réaliser le 31/10/2020 au soir + test en ligne
*Bonus: possible d'aller plus loin jusqu'au 16/11/2020 08h00 pour des points bonus.*


## Introduction

Personnalités ayant marquer la matière: [John McCarthy](https://fr.wikipedia.org/wiki/John_McCarthy), [Marvin Minsky](https://fr.wikipedia.org/wiki/Marvin_Minsky), [Symour Papert](https://fr.wikipedia.org/wiki/Seymour_Papert), [Alan Turing](https://fr.wikipedia.org/wiki/Alan_Turing), etc. .

**Qu'est ce que l'intelligence?**
> "La capacité à acquérir et appliquer des connaissances et des savoirs."  
> [Dictionnaire Oxford](https://www.oxfordlearnersdictionaries.com/)


**Qu'est ce que l'intelligence artificielle?**
> Remplacer une tâche intellectuelle, faite par un être humain, par une faite par une machine.  
> Source manquante

**Qu'est ce qu'apprendre?**
> "Améliorer sa performance par l'expérience."  
> [Herbert Simon](https://fr.wikipedia.org/wiki/Herbert_Simon)

**Qu'est ce que le Machine-Learning?**

> "Des machines qui améliorent automatiquement leur performance par l’expérience."  
> [Herbert Simon](https://fr.wikipedia.org/wiki/Herbert_Simon)
  


Historique:

- 1996: *Jeu d'échecs*, [Kasparov](https://fr.wikipedia.org/wiki/Garry_Kasparov)-[Deep Blue](https://fr.wikipedia.org/wiki/Deep_Blue) 4-2 (Kasparov a quand même gagner)
- 1997: *Jeu d'échecs*, Kasparov-Deeper Blue 2.5-3.5 (Deeper-Blue a gagner)
- 2011: *Jeopardy!*, humains-Watson
- 2016: *Jeu de Go*, Sedol-AlphaGo 1-4
- Plus récemment: *Jeu de Go*, AlphaGoZero-AlphaGo 100-0

[Vidéo ScienceEtonnante](https://www.youtube.com/watch?v=xuBzQ38DNhE)

!!! tip "Blague"
    **Quelle est la différence entre l'automatisation et l'intelligence artificielle?**  
    Automatisation: ce qu'on sait faire avec une machine  
    Intelligence artificielle: ce qu'on voudrait faire avec une machine


<center>
  <figure>
    <img src="https://i.imgur.com/YjyUYnK.png"
    alt="Image introuvable"
    width="400"
    height="400"
    >
    <figcaption><i>Figure 1: L'intelligence artificielle</i></figcaption>
  </figure>
</center>

!!! faq "Questions irrésolues:"
    <b>Comment une machine peut-elle:

    - optimiser un jeu de paramètres?
    - s'adapter a son environnement? 
    - choisir entre plusieurs option?
    - fournir des solutions à des questions posées?</b>


## Renforcement d'apprentissage

Renforcement d'apprentissage: une autre manière d'apprendre.

### Généralités

!!! faq "Questions"
    **Comment peut on faire a meilleure action possible au bon moment?**  
    D'abord:  
    Qu'est ce que la meilleure action?  
    qu'est ce que le bon moment?

Notre environnent change en permanence donc l'algorithme et/ou les paramètres choisis peuvent devenir faux.  
Peut-être pourrait on tirer parti de l’expérience passée

**Comment apprendre?**

> L'apprentissage supervisé est une tâche d'apprentissage automatique consistant à apprendre une fonction de prédiction à partir d'exemples annotés.  
> Source: [Wikipédia](https://fr.wikipedia.org/wiki/Apprentissage_supervis%C3%A9)
<center>
  <figure>
    <img src="https://i.imgur.com/Schz2rk.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 2: Apprentissage supervisé</i></figcaption>
  </figure>
</center>

> Dans le domaine informatique et de l'intelligence artificielle, l'apprentissage non supervisé désigne la situation d'apprentissage automatique où les données ne sont pas étiquetées. Il s'agit donc de découvrir les structures sous-jacentes à ces données non étiquetées.  
> Source: [Wikipédia](https://fr.wikipedia.org/wiki/Apprentissage_non_supervis%C3%A9)
<center>
  <figure>
    <img src="https://i.imgur.com/fwlEgZH.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 3: Apprentissage non supervisé</i></figcaption>
  </figure>
</center>

>En intelligence artificielle, plus précisément en apprentissage automatique, l'apprentissage par renforcement consiste, pour un agent autonome (robot, etc.), à apprendre les actions à prendre, à partir d'expériences, de façon à optimiser une récompense quantitative au cours du temps. L'agent est plongé au sein d'un environnement, et prend ses décisions en fonction de son état courant. En retour, l'environnement procure à l'agent une récompense, qui peut être positive ou négative.  
> Source: [Wikipédia](https://fr.wikipedia.org/wiki/Apprentissage_par_renforcement)
<center>
  <figure>
    <img src="https://i.imgur.com/l3c9Oty.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 4: Apprentissage par récompense</i></figcaption>
  </figure>
</center>

**Pourquoi un automate?**  
- Pour fixer un but a atteindre pour l'agent  
- ou bien pour appliquer des règles simples, sans but réel (comportement émergent)

Il est essentiel de pouvoir valoriser un action qui nous fait passer d'un état a un autre.
<center>
  <figure>
    <img src="https://i.imgur.com/KRSFQAB.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 5: Valorisation d'action</i></figcaption>
  </figure>
</center>

Pour la valorisation il est essentiel de se référer au gain a court terme et au gain a long terme. Il faut pouvoir prendre en compte plus que ce que je peux voir maintenant. Exemple: aux échecs le sacrifice de la reine car on sait que plus tard qu'on obtiendra un avantage ou une victoire. **Il faudrait pouvoir prendre en compte toutes les conséquences de toutes les actions possibles.**

- Résoudre des [équations de Bellman](https://en.wikipedia.org/wiki/Bellman_equation) (1957)
- Programmations dynamiques, [processus décisionnels de Markov](https://fr.wikipedia.org/wiki/Processus_de_d%C3%A9cision_markovien)
- En pratique c'est complexe et coûteux (en temps de calcul) pour des systèmes qui peuvent avoir des milliards d'états différents
- et peut-être que l'on ignore des éléments
- itérer pour approximer la solution optimale


### Agent

Agent: de la théorie à la pratique

Pour décider l'action a réaliser on va s'appuyer sur des calculs probabilistes:
<center>
  <figure>
    <img src="https://i.imgur.com/dXL5AQo.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 6: Tableau de choix d'action</i></figcaption>
  </figure>
</center>

Cette méthode permet d'obtenir une fonction d'utilité qui nous guidera sur la meilleure action à réaliser. Cette fonction nous donne la meilleure espérance de gain dans le futur. Dans notre cas c'est l'action 2 qui permettra le meilleure gain immédiat mais aussi dans le futur. Alors que l'action 3 nous donne peu de gain a court terme mais un gain conséquent a long terme.

On qualifie cette fonction:  

Avec une somme finie:
<font size="2">
$utility(state_t, action)=E(reward(state_t, action)+max \sum{future\_reward})$
</font>  

Avec une somme infinie:
<font size="2">
$utility(state_t, action)=E(reward(state_t, action)+max \sum_{i=1}^{\infty}{attenuate^i.future\_reward_i})$
</font>  

**Meilleure estimateur: fonction d'utilité !**

avec:

- E l'influence de l'environnement
- $attenuate$ le facteur d'atténuation
On en déduit:

<font size="2">
$\sum_{i=1}^{\infty}{attenuate^i.future\_reward_i} = \sum_{i=1}^{1}{attenuate^0.future\_reward_i} + \sum_{i=2}^{\infty}{attenuate^{i-1}.future\_reward_i}$
</font>  

On peut encore réécrire:
<font size="2">
$utility(state_t, action)=E(reward(state_t, action)+attenuate.max_{action}utility(state_{t+1},action))$
</font>  

On obtient ici une récursion inversée

<font size="2">
$utility_{t+1}(state_t,action) = (1-step).utility_t(state_t,action)+step.(reward(state_t,action)+attenuate.max_{action}utility(state_{t+1},action))$
</font>  


Le terme $utility_{t+1}(state_t,action)$ représente la **progression itérative**  


Le terme $step$ représente le taux d'apprentissage  
Le terme $attenuate.max_{action}utility(state_{t+1},action))$ représente la capacité de "deviner le futur"

On va pouvoir changer la probabilité de faire une action dans un état donnée.

### Exemple du moustique

<center>
  <figure>
    <img src="https://i.imgur.com/GTuaCqx.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 7: Relation action/état du moustique</i></figcaption>
  </figure>
</center>


<center>
  <figure>
    <img src="https://i.imgur.com/Sy4GFO3.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 8: Tableau d'action/état du moustique</i></figcaption>
  </figure>
</center>


On va tester le programme fourni dans une VM, est nécessaire d'installer la librairie freeglut3-dev: `sudo apt install freeglut3-dev`.

Pour lancer la simulation il suffit de make le projet puis `./reinflearn`

en tapant 0, 1, 2, 3 ,4 ,5 ,6 on peut choisir le facteur d'apprentissage du moustique.

On remarque qu'a 0 il se comporte comme un "marcheur ivre".

En tapant "a" il est possible de faire varier la position de la zone de confort du moustique.

### Exemple du Jeu de Nim

En résolvant ce jeu on peut "expliquer" comment jouer a un automate.

<center>
  <figure>
    <img src="https://i.imgur.com/65AMVdY.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 9: Tableau de résolution du jeu de Nim</i></figcaption>
  </figure>
</center>

## Algorithme génétiques

**Comment une machine peut-elle optimiser un jeu de paramètres?**

> Les algorithmes génétiques appartiennent à la famille des algorithmes évolutionnistes. Leur but est d'obtenir une solution approchée à un problème d'optimisation, lorsqu'il n'existe pas de méthode exacte (ou que la solution est inconnue) pour le résoudre en un temps raisonnable. Les algorithmes génétiques utilisent la notion de sélection naturelle et l'appliquent à une population de solutions potentielles au problème donné. La solution est approchée par « bonds » successifs, comme dans une procédure de séparation et évaluation (branch & bound), à ceci près que ce sont des formules qui sont recherchées et non plus directement des valeurs.  
> Source: [Wikipédia](https://fr.wikipedia.org/wiki/Algorithme_g%C3%A9n%C3%A9tique)

Exemple d'utilisation: 

- Générer des paramètres pour choisir la meilleure configuration d'automates logiciels;
- Résoudre l'optimisation de conditions de frittage dans un espace de solutions de dimension 17;
- Résoudre un "problème inverse mal posé" sur la reconstruction de volumes à partir d'images 2D.


On part d'un jeu de solutions possibles, on sélectionne 2 solutions possible que l'on va croiser. On décide de garder ou non cette solution, et on recommence en ajoutant ou non cette solution dans les solutions possibles.

<center>
  <figure>
    <img src="https://i.imgur.com/FO6swgB.png"
    alt="Image introuvable"
    width="500"
    height="500"
    >
    <figcaption><i>Figure 10: Système de croisement de solutions</i></figcaption>
  </figure>
</center>

### Fonction de fitness

Fonction de fitness: La fitness mesure la qualité de l'individu exprimée sous forme d'un nombre ou d'un vecteur. On dit qu'un individu i est meilleur que l'individu j quand i est plus proche de la solution que j.

Trouver la bonne métrique est parfois difficiles. Parfois changer la fonction de fitness après un moment. Elle doit être suffisamment sélective sans l'être trop.

La sélection probabiliste des individus est très importante.

