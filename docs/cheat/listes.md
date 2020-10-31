# Listes

## Liste numérotée

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


## Liste à puces

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

## Tasklist

!!! example "Tasklist"

    === "Code"
        ```md
        * [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
        * [ ] Vestibulum convallis sit amet nisi a tincidunt
            * [x] In hac habitasse platea dictumst
            * [x] In scelerisque nibh non dolor mollis congue sed et metus
            * [ ] Praesent sed risus massa
        * [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque
        ```
    === "Rendu" 
        * [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
        * [ ] Vestibulum convallis sit amet nisi a tincidunt
            * [x] In hac habitasse platea dictumst
            * [x] In scelerisque nibh non dolor mollis congue sed et metus
            * [ ] Praesent sed risus massa
        * [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque

