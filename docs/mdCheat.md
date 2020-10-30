# <center>Markdown Cheat Sheet</center>

[util](http://markdowntable.com/)
https://www.markdownguide.org/basic-syntax/
http://www-lmpa.univ-littoral.fr/~marion/docs-and-tips/cheatsheet/

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




## Titres

```
# Grand titre
## Moyen Titre
### Petit Titre
#### Petit Sous Titre
##### Très Petit Titre
###### Très Petit Sous titre
```


## Lists

```
1. Premièrement
2. Puis on sous-liste:
    - Liste
      + Un élément
1. Ensuite (les nombres n'importent pas)
4. Enfin un dernier item

</a> #On arrête la liste
```



## Links


```
[Lien en ligne](https://www.pouet.com)

[Lien en référence][dU tExT eN liEn] #Non case-sensitive

[Référence a un fichier](../blob/master/LICENSE)

[Référence grâce a un nombre][1]

On référence le lien direct [lien direct].

[du text en lien]: https://www.pouet.com
[1]: https://www.pouet.com
[lien direct]: https://www.pouet.com
```


## Images

```
Image en ligne:
![alt text](https://www.pouet.com/images/image.png "Logo Title Text 1")

Image en référence:
Reference-style: 
![alt text][logo]

[logo]: https://www.pouet.com/images/image.png "Logo Title Text 2"


Version HTML:

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


## Code and Syntax Highlighting

## Tables

## Blockquotes

## Inline HTML

## Horizontal Rule

## Line Breaks

## YouTube Videos

## Tips

```
!!! keyword "titre du bloc facultatif (keyword ou keyword)"
    blabla
```

!!! note "note ou seealso"
    blabla

!!! tip "tip ou hint ou important"
    Ceci est un tip

!!! info "info ou todo"
    Ceci est une info

!!! help "question ou help ou faq"
    Ceci est une question

!!! summary "summary"
    Ceci est un exemple

!!! warning "warning ou caution ou attention"
    Ceci est un exemple

!!! failure "failure ou fail ou missing"
    Ceci est un exemple

!!! done "check ou done"
    Ceci est un exemple

!!! danger "danger ou error"
    Ceci est un exemple

!!! bug "bug"
    Ceci est un exemple

!!! quote "quote"
    Ceci est un exemple










[Link]:https://bit.ly/3kpNaJl
