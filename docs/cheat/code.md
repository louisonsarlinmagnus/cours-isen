# Code

## Ligne de code

Il est possible de définir une ligne de code dans une phrase en l'encadrant avec des ` .

!!! example "Ligne de code"

    Il est possible de coloriser du code dans un ligne en précédant le code par `#!<language>`:
    === "Markdown"
        <pre><code>La fonction \`#!python range()\` permet de générer un séquence de nombres.</code></pre>
    === "Rendu"
        La fonction `#!python range()` permet de générer un séquence de nombres.



## Bloc de code

!!! example "Bloc de code"

    === "Markdown"
        ````md
        ```java hl_lines="1-2 5 7" linenums="1"
        public class HelloWorld {
          // Définition de la fonction main
          public static void main(String[] arg){
            // Affichage du commentaire Hello world dans la fenêtre de commande
            System.out.println("Hello world");
          }
        } 
        ```
        ````

    === "HTML"
        ```html
        <pre><code>
            public class HelloWorld {
                      // Définition de la fonction main
                      public static void main(String[] arg){
                        // Affichage du commentaire Hello world dans la fenêtre de commande
                        System.out.println("Hello world");
                      }
                    } 
        </code></pre>
        ```

    === "Rendu"
        ```java hl_lines="1-2 5 7" linenums="1"
        public class HelloWorld {
          // Définition de la fonction main
          public static void main(String[] arg){
            // Affichage du commentaire Hello world dans la fenêtre de commande
            System.out.println("Hello world");
          }
        } 
        ```

!!! tip "Suligner du code"
    Il est possbile de surligner du code en ajoutant `hl_lines="1-2 5 7"` à côté du language choisi.

!!! tip "Ajouter les numeros de ligne"
    Il est possible d'ajouter les numéros de ligne en ajoutant `linenums="1"` à côté du language choisi.

!!! tip "Ajouter un titre"
    Il est possible d'ajouter un titre (nom du fichier par exemple) en ajoutant `title="titre.py"` par exemple.

!!! tip "Poupée russe"
    Il est possible d'emboiter des blocs de code en ajoutant un ` a chaque incrément.
