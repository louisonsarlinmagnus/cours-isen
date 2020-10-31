# Images

!!! example "Image simple"

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


!!! tip "Position de l'image"
    Il est possible d'aligner une image sur la droite ou la gauche avec le code suivant

    === "Code"
        ```md
        ![Placeholder](https://dummyimage.com/200x100/eee/aaa){: align=right }
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
        nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
        massa, nec semper lorem quam in massa.
        ```

    === "Rendu"
        ![Placeholder](https://dummyimage.com/200x100/eee/aaa){: align=right }
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
        nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
        massa, nec semper lorem quam in massa.
