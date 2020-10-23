# DEV-OPS

## Mise en jambes

###DOCKER  
Docker c koi? : **Permet de mettr dans un container un micro-service**  
- `docker build -t louisonsarlinmagnus/yncrea-hellomicro:latest .`: On build notre image docker  
- `docker run -p 8080:8080 -t <adresse_Docker_Host>/yncrea-hellomicro:latest` : permet de lancer l'image Docker dans un container sur le port 8080.  

###Minikube
Minikube c koi? : **Permet la gestion des DOCKER containers (pods)**  
- `minikube start` : On lance minikube  
- `minikube ip` : On note l'ip de notre minikube  
- `eval $(minikube docker-env)` : Utiliser le deamon docker de minikube (pas celui local)  
- `env | grep DOCKER` : affiche (pour verif) les variable environnement de DOCKER  
- `kubectl apply -f deployment.yaml`: Déploi le container selon les paramètre de deployment  

###HELM
Helm c koi? : **Permet de packager un déploiment kubernetes**  
- `helm install silly-unicorn src/helm/chart/yncrea-hellomicro`: Permet de packager notre micro-service *yncrea-hellomicro* et d'y référencer via le nom *silly unicorn*.  
- `helm uninstall silly-unicorn` : Permet de supprimer le package *silly-unicorn*.  
- `helm upgrade silly-unicorn src/helm/chart/yncrea-hellomicro` : Permet de mettre a jour le package.  


## Commandes utiles

- `docker stop <id_container>` : stop le container Docker en cours  
- `docker container ls` : obtenir l'id du container Docker  
- `mvn clean install` : build l'image Docker  
- `docker images` : pour voir les images Docker existantes  
- `docker run -p 8080:8080 -t <adresse_Docker_Host>/yncrea-hellomicro:latest` : permet de lancer l'image Docker `<adresse_Docker_Host>/yncrea-hellomicro:latest` sur le port 8080.  
- `<adresse_Docker_Host>` est fourni par `minikube ip`.  
- `kubectl apply -f src/kubernetes/deployment.yaml` : déployer l'application  
- `kubectl get deployment` : pour vérifier que l'application est déployé  
- `kubectl apply -f src/kubernetes/service.yaml` : déployer le service  
- `kubectl get svc` : Afficher les services déployés (utile pour récupérer le `<port_minikube>`)  
- `<minikube_ip>:<port_minikube>` : pour acceder au micro-service  
- `kubectl.exe scale deployment/yncrea-hellomicro --replicas=3` : pour dépoloyer 3 fois le service
- `kubectl edit deployment yncrea-hellomicro` : pour modifier les variables d'environnement
- `kubectl create secret generic yncrea-hellomicro-secret --from-literal=secret.txt="my very secret secret agent name"` : ajout d'un secret
- `kubectl get secrets`: Pour récup les secret créés
- `kubectl delete secret yncrea-hellomicro-secret`: Pour supprimer un secret



Au début on a vu spring boot: pour faire un changement faut tout faitre a la main
Puis docker je suis plus dépendant de la plateforme
Kubernetes gère les docker
Kube permet de créer un service avec plusieur conteneurs
Kube permet de config des applications
Kube peut gèrer les secrets
SpringBoot>Docker>Kubernetes(Pods>Service)>helmCharts