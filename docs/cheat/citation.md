## Blocs de citation

!!! example "Bloc de citation"

    === "Markdown"
        ```md
        > Un problème sans solution est un problème mal posé.  
        > Albert Einstein
        ```
    === "HTML"
        ```html
        <blockquote>
        Un problème sans solution est un problème mal posé.<br>
        Albert Einstein
        </blockquote>
        ```
    === "Rendu"
        > Un problème sans solution est un problème mal posé.  
        > Albert Einstein

## Note de bas de page

Les notes de bas de pages permettent de donner des précisions sans casser le discours:

*Code*:

```md
Ceci est un façon[^1] de définir une note de bas de page.  
Ceci est du texte intermédiaire  
Ceci est une autre façon[^t] de définir une note de bas de page.  
Et voici encore du text.  
Encore un peu.  

[^1]: La première façon est numérique
[^t]: Mais il est possible de mettre des caractères
```

*Rendu*:

Ceci est un façon[^1] de définir une note de bas de page.  
Ceci est du texte intermédiaire  
Ceci est une autre façon[^t] de définir une note de bas de page.  
Et voici encore du text.  
Encore un peu.  

[^1]: La première façon est numérique
[^t]: Mais il est possible de mettre des caractères

!!! info "Ajout de l'extension"
    Il est nécessaire d'ajouter dans `mkdocs.yml` sous `markdown_extensions` l'option `footnotes`