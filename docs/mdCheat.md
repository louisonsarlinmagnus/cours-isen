# <center>Markdown Cheat Sheet</center>

## Résumé

| Effet                | Md              | HTML                             |
|--:-------------------|--:--------------|--:-------------------------------|
| Titre                | `#` (jusqu'a 6) | `<h1>` (jusqu'a `<h6>`)          |
| **Gras**             | `**text**`      | `<b>text<b>`                     |
| <ins>Souligner</ins> | ....            | `<ins>text</ins>`                |
| *Italique*           | `*text*`        | `<i>text</i>`                    |
| ***Gras italique***  | `***text***`    | `<b><i>text</i></b>`             |
| `code`               | \`text\`        | `<code>code</code>`              |
| [Link]               | `[Link]`        | `<a href=www.truc.com>Link</a>`  |
|  Quote               | `> text`        | `<<blockquote>text</blockquote>` |
|  ~~Rayer~~           | `~~text~~`      | `<s>text</s>`                    |
|  $Formule$           | `$text$`        | ....                             |




## Titres


!!! example "Titres"

    === "Markdown"
        ```md
        # Grand titre
        ## Moyen Titre
        ### Petit Titre
        #### Petit Sous Titre
        ##### Très Petit Titre
        ###### Très Petit Sous Titre
        ```

    === "HTML"
        ````html
        <h1>Grand titre</h1>
            <h2>Moyen Titre</h2>
                <h3>Petit Titre</h3>
                    <h4>Petit Sous Titre</h4>
                        <h5>Très Petit Titre</h3>
                            <h6>Très Petit Sous Titre</h4>
        ````

    === "Rendu"
        <h1>Grand titre</h1>
            <h2>Moyen Titre</h2>
                <h3>Petit Titre</h3>
                    <h4>Petit Sous Titre</h4>
                        <h5>Très Petit Titre</h3>
                            <h6>Très Petit Sous Titre</h4>


## Listes

### Liste numérotée

!!! example "Liste numérotée"

    === "Markdown"
        ```md
        1. Premièrement
        2. Puis le second
        1. Ensuite (les nombres n'importent pas)
        4. Enfin un dernier item
        </a> #On arrête la liste
        ```

    === "HTML"
        ````html
        <ol>
          <li>Premièrement</li>
          <li>Puis le second</li>
          <li>Ensuite</li>
          <li>Enfin un dernier item</li>
        </ol>
        ````

    === "Rendu"
        1. Premièrement
        2. Puis le second:
        1. Ensuite (les nombres n'importent pas)
        4. Enfin un dernier item


### Liste à puces

!!! example "Liste à puces"

    === "Markdown"
        ```md
        - Premier
        - Second
            + Troisième
        ```

    === "HTML"
        ```html
        <ul>
            <li>Premier</li>
            <li>Second le second</li>
            <ul>
                <li>Troisième</li>
            </ul>
        </ul>
        ```

    === "Rendu"
        - Premier
        - Second
            + Troisième


## Liens

### Liens externes

!!! example "Liens externes"

    === "Markdown"
        ```md
        [Lien en ligne](https://www.pouet.com)
        [Lien en référence][dU tExT eN liEn] #Non case-sensitive
        [Référence grâce a un nombre][1]
        On référence le lien direct [lien direct].
        [du text en lien]: https://www.pouet.com
        [1]: https://www.pouet.com
        [lien direct]: https://www.pouet.com
        ```

    === "HTML"
        ```html
        <a href="https://www.pouet.com">Lien en ligne</a>
        <a href="https://www.pushaune.com" target="_blank">Pour ouvrir dans un nouveau onglet</a>
        ```


### Liens internes

!!! example "Liens externes"

    === "Markdown"
        ```md
        [Référence a un fichier](../blob/master/LICENSE)
        [Réference a un paragraphe](#liens)
        ```

    === "HTML"
        ```html
        <a href="../blob/master/LICENSE">Référence a un fichier</a>
        <a href="#liens">Réference a un paragraphe</a>
        ```


## Images

!!! example "Images"

    === "Markdown"
        ```md
        Image en ligne:
        ![alt text](https://www.pouet.com/images/image.png "Logo Title Text 1")

        Image en référence:
        Reference-style: 
        ![alt text][logo]

        [logo]: https://www.pouet.com/images/image.png "Logo Title Text 2"
        ```

    === "HTML"
        ```html
        <center>
          <figure>
            <img src="https://www.pouet.com/images/image.png"
            alt="Image introuvable"
            width="600"
            height="600"
            >
            <figcaption><i>Figure x: Description de l'image</i></figcaption>
          </figure>
        </center>
        ```


## Code

!!! example "Example"

    === "Markdown"
        ````md
        ```language linenums="1"
        du code dans un language  
        ```
        ````

    === "HTML"
        ```html
        <pre><code>
            Du code
        </code></pre>
        ```

    === "Rendu"
        ```java linenums="1"
        public class HelloWorld {
          // Définition de la fonction main
          public static void main(String[] arg){
            // Affichage du commentaire Hello world dans la fenêtre de commande
            System.out.println("Hello world");
          }
        } 
        ```

!!! tip "Poupée russe"
    Il est possible d'emboiter des blocs de code en ajoutant un ` a chaque incrément.

## LaTex

!!! tip "LaTex"
    Pour utiliser le LaTex il suffit d'entourer la formule par le symbole '$'.

| Opération        | LaTex         | Rendu           |
|------------------|---------------|-----------------|
| Signe $\times$   | \times        | $\times$        |
| Puissance        | a^{b}         | $a^{b}$         |
| Indice           | a_{b}         | $a_{b}$         |
| Racine           | \sqrt[n]{x}   | $\sqrt[n]{x}$   |
| Fraction         | \frac{a}{c}   | $\frac{a}{c}$   |
| Somme            | \sum_{i=0}^n  | $\sum_{i=0}^n$  |
| Produit          | \prod_{i=0}^n | $\prod_{i=0}^n$ |
| Fraction         | \frac{a}{c}   | $\frac{a}{c}$   |
| Intégrale        | \int_a^b      | $\int_a^b$      |
| Caractères grecs | \alpha        | $\alpha$        |
| Fonction trigo   | \sin          | $\sin$          |
| Exponentielle    | \exp(x)       | $\exp(x)$       |
| Infini           | \infty        | $\infty$        |
| Vecteur          | \vec{a}       | $\vec{a}$       |




## Tableaux

[Table formatter util](http://markdowntable.com/)  

!!! example "Example"

    === "Markdown"
        ```md
        | Firstname | Lastname | Age |
        |-----------|----------|-----|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |
        ```

    === "HTML"
        ```html
         <table style="width:100%">
          <tr> 
            <th>Firstname</th>   <!--th pour les headers-->
            <th>Lastname</th>
            <th>Age</th>
          </tr>
          <tr>                   <!--tr pour les lignes-->
            <td>Jill</td>
            <td>Smith</td>
            <td>50</td>          <!--td pour les colonnes-->
          </tr>
          <tr>
            <td>Eve</td>
            <td>Jackson</td>
            <td>94</td>
          </tr>
        </table> 
        ```

    === "Rendu"
        | Firstname | Lastname | Age |
        |-----------|----------|-----|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |


## Diagrammes Mermaid

### Flowchart

!!! example "Flowchart"

    === "Code"
        ````
        ```mermaid
        graph TD;
            A-->B;
            A-->C;
            B-->D;
            C-->D;
        ```
        ````

    === "Rendu"
        ```mermaid
            graph TD;
                A-->B;
                A-->C;
                B-->D;
                C-->D;
        ```


### Sequence diagram


!!! example "Flowchart"

    === "Code"
        ````
        ```mermaid
        sequenceDiagram
            participant Alice
            participant Bob
            Alice->>John: Hello John, how are you?
            loop Healthcheck
                John->>John: Fight against hypochondria
            end
            John-->>Alice: Great!
            John->>Bob: How about you?
            Bob-->>John: Jolly good!
        ```
        ````

    === "Rendu"
        ```mermaid
            sequenceDiagram
                participant Alice
                participant Bob
                Alice->>John: Hello John, how are you?
                loop Healthcheck
                    John->>John: Fight against hypochondria
                end
                John-->>Alice: Great!
                John->>Bob: How about you?
                Bob-->>John: Jolly good!
        ```


### Gantt diagram

!!! example "Gantt diagram"

    === "Code"
        ````
        ```mermaid
        gantt
            title A Gantt Diagram
            dateFormat  YYYY-MM-DD
            section Section
            A task           :a1, 2014-01-01, 30d
            Another task     :after a1  , 20d
            section Another
            Task in sec      :2014-01-12  , 12d
            another task      : 24d
        ```
        ````

    === "Rendu"
        ```mermaid
            gantt
                title A Gantt Diagram
                dateFormat  YYYY-MM-DD
                section Section
                A task           :a1, 2014-01-01, 30d
                Another task     :after a1  , 20d
                section Another
                Task in sec      :2014-01-12  , 12d
                another task      : 24d
        ```

### Class diagram

!!! example "Class diagram"

    === "Code"
        ````
        ```mermaid
        classDiagram
              Animal <|-- Duck
              Animal <|-- Fish
              Animal <|-- Zebra
              Animal : +int age
              Animal : +String gender
              Animal: +isMammal()
              Animal: +mate()
              class Duck{
                  +String beakColor
                  +swim()
                  +quack()
              }
              class Fish{
                  -int sizeInFeet
                  -canEat()
              }
              class Zebra{
                  +bool is_wild
                  +run()
              }
        ```
        ````

    === "Rendu"
        ```mermaid
            classDiagram
                  Animal <|-- Duck
                  Animal <|-- Fish
                  Animal <|-- Zebra
                  Animal : +int age
                  Animal : +String gender
                  Animal: +isMammal()
                  Animal: +mate()
                  class Duck{
                      +String beakColor
                      +swim()
                      +quack()
                  }
                  class Fish{
                      -int sizeInFeet
                      -canEat()
                  }
                  class Zebra{
                      +bool is_wild
                      +run()
                  }
        ```


### Git graph

!!! example "Git graph"

    === "Code"
        ````
        ```mermaid
        gitGraph:
        options
        {
            "nodeSpacing": 150,
            "nodeRadius": 10
        }
        end
        commit
        branch newbranch
        checkout newbranch
        commit
        commit
        checkout master
        commit
        commit
        merge newbranch
        ```
        ````

    === "Rendu"
        ```mermaid
        gitGraph:
        options
        {
            "nodeSpacing": 150,
            "nodeRadius": 10
        }
        end
        commit
        branch newbranch
        checkout newbranch
        commit
        commit
        checkout master
        commit
        commit
        merge newbranch
        ```


### Entity Relationship Diagram

!!! example "Entity Relationship Diagram"

    === "Code"
        ````
        ```mermaid
        erDiagram
            CUSTOMER ||--o{ ORDER : places
            ORDER ||--|{ LINE-ITEM : contains
            CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
        ```
        ````

    === "Rendu"
        ```mermaid
            erDiagram
                CUSTOMER ||--o{ ORDER : places
                ORDER ||--|{ LINE-ITEM : contains
                CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
        ```


### User Journey Diagram

!!! example "User Journey Diagram"

    === "Code"
        ````
        ```mermaid
        journey
            title My working day
            section Go to work
              Make tea: 5: Me
              Go upstairs: 3: Me
              Do work: 1: Me, Cat
            section Go home
              Go downstairs: 5: Me
              Sit down: 5: Me
        ```
        ````

    === "Rendu"
        ```mermaid
            journey
                title My working day
                section Go to work
                  Make tea: 5: Me
                  Go upstairs: 3: Me
                  Do work: 1: Me, Cat
                section Go home
                  Go downstairs: 5: Me
                  Sit down: 5: Me
        ```

## SuperFences

!!! example "SuperFences"

    === "Code"
        ```
        !!! example "SuperFences"
                    === "Bash"
                        ```bash
                        #!/bin/bash
                        echo "Hello world!"
                        ```
                    === "C"
                        ```c
                        #include <stdio.h>
                        int main(void) {
                          printf("Hello world!\n");
                        }
                        ```
                    === "C++"
                        ```cpp
                        #include <iostream>
                        int main() {
                          std::cout << "Hello world!" << std::endl;
                          return 0;
                        }
                        ```
                    === "C#"
                        ```cs
                        using System;
                        class Program {
                          static void Main(string[] args) {
                            Console.WriteLine("Hello world!");
                          }
                        }
                        ```
        ```

    === "Rendu"
        !!! example "SuperFences"
            === "Bash"
                ```bash
                #!/bin/bash
                echo "Hello world!"
                ```
            === "C"
                ```c
                #include <stdio.h>
                int main(void) {
                  printf("Hello world!\n");
                }
                ```
            === "C++"
                ```cpp
                #include <iostream>
                int main() {
                  std::cout << "Hello world!" << std::endl;
                  return 0;
                }
                ```
            === "C#"
                ```cs
                using System;
                class Program {
                  static void Main(string[] args) {
                    Console.WriteLine("Hello world!");
                  }
                }
                ```


## Tasklist

## Highlight Example

## Nth Line Example

## Special Line Example





## Blocs de citation

Markdown:
```
> Un problème sans solution est un problème mal posé.  
> Albert Einstein
```

HTML:
```html
<blockquote>
Un problème sans solution est un problème mal posé.<br>
Albert Einstein
</blockquote>
```

## Règle horizontale

```
***
---
___
```

## Smileys

| Smiley       | Rendu      |
|--:-----------|--:---------|
| `:alien:`    | :alien:    |
| `:yum:`      | :yum:      |
| `:confused:` | :confused: |
| `:smirk:`    | :smirk:    |
| `:kiss:`     | :kiss:     |
| `:frog:`     | :frog:     |
| `:fr:`       | :fr:       |
| `:gb:`       | :gb:       |
| `:tongue:`   | :tongue:   |
| `:computer:` | :computer: |

[Liste des smileys](https://gist.github.com/rxaviers/7360908)


## Videos YouTube

Markdown:
```
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
```

HTML:
```html
<a 
    href="https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE
    "target="_blank">
        <img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
        alt="IMAGE ALT TEXT HERE"
        width="240"
        height="180"
        border="10"
        />
</a>
```

## Bloc Spoiler

```
??? tip
    Ceci est un spoiler a dérouler
```

??? tip
    Ceci est un spoiler a dérouler

## Bloc d'alerte

```
!!! keyword "titre du bloc facultatif (keyword ou keyword)"
    blabla
```

!!! note "note ou seealso"
    blabla

!!! tip "tip ou hint ou important"
    blabla

!!! info "info ou todo"
    blabla

!!! help "question ou help ou faq"
    blabla

!!! summary "summary"
    blabla

!!! warning "warning ou caution ou attention"
    blabla

!!! failure "failure ou fail ou missing"
    blabla

!!! done "check ou done"
    blabla

!!! danger "danger ou error"
    blabla

!!! bug "bug"
    blabla

!!! quote "quote"
    blabla

!!! example "example"
    blabla
