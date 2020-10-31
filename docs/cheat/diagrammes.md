# Diagrammes Mermaid

## Flowchart

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


## Sequence diagram


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


## Gantt diagram

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

## Class diagram

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


## Git graph

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


## Entity Relationship Diagram

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


## User Journey Diagram

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
