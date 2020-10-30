# <center>Markdown Cheat Sheet</center>

[cheatsheet](http://www-lmpa.univ-littoral.fr/~marion/docs-and-tips/cheatsheet/)  

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

```
# Grand titre
## Moyen Titre
### Petit Titre
#### Petit Sous Titre
##### Très Petit Titre
###### Très Petit Sous titre
```


## Listes

```
1. Premièrement
2. Puis on sous-liste:
    - Liste
      + Un élément
1. Ensuite (les nombres n'importent pas)
4. Enfin un dernier item

</a> #On arrête la liste
```



## Liens

### Liens externes

```
[Lien en ligne](https://www.pouet.com)

[Lien en référence][dU tExT eN liEn] #Non case-sensitive

[Référence grâce a un nombre][1]

On référence le lien direct [lien direct].

[du text en lien]: https://www.pouet.com
[1]: https://www.pouet.com
[lien direct]: https://www.pouet.com
```

### Liens internes

```
[Référence a un fichier](../blob/master/LICENSE)

[Réference a un paragraphe](#liens)

```


## Images

!!! example "Injecting Classes"

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

Markdown:  
```md
Image en ligne:
![alt text](https://www.pouet.com/images/image.png "Logo Title Text 1")

Image en référence:
Reference-style: 
![alt text][logo]

[logo]: https://www.pouet.com/images/image.png "Logo Title Text 2"
```

HTML:  
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


!!! tip "Ajout des numeros de ligne"
    Il suffit d'ajouter `linenums="num_premiere_ligne"` après le language
   


Markdown:  
<code>
\```language  
du code dans un language  
\```
</code>

HTML:  
```html
<pre><code>
    Du code
</code></pre>
```

## Tableaux

[Table formatter util](http://markdowntable.com/)  


Markdown:  
```
| Firstname | Lastname | Age |
|-----------|----------|-----|
| Jill      | Smith    | 50  |
| Eve       | Jackson  | 94  |
```

HTML:
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

## Diagrammes UML

<code>
\```mermaid<br>
graph TD<br>
    A[Hard] -->|Text| B(Round)<br>
    B --> C{Decision}<br>
    C -->|One| D[Result 1]<br>
    C -->|Two| E[Result 2]<br>
\```
</code>


[Marion](http://www-lmpa.univ-littoral.fr/~marion/docs-and-tips/cheatsheet/#new-2019-autres-tests)

[md synthax](http://facelessuser.github.io/PyMdown/user-guide/markdown-syntax/)

[pydown](https://squidfunk.github.io/mkdocs-material/extensions/pymdown/)

## LaTex

## SuperFences

!!! example "Injecting Classes"

    === "HTML"
        ```html
        <table class="extra-class highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre><span></span>1</pre></div></td><td class="code"><div class="extra-class highlight"><pre><span></span><code><span cv></td><td class="code"><div class="extra-class highlight"><pre><span></span><code><span class="kn">import</span> <spanlass="kn">import</span> <span class="nn">hello_world</span>\n</code></pre></div>\n</td></tr></table>
        ```

    === "Markdown"
        ````
        ```{.python .extra-class linenums="1"}
        import hello_world
        ```
        ````


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
