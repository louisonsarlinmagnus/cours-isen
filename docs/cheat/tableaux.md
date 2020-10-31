## Tableaux simple

[Table formatter util](http://markdowntable.com/)  

!!! example "Tableau simple"

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

## Configuration

!!! info "Centrage des éléments du tableau"

    La position des ':' dans le tableau définira le centrage appliqué aux éléments du tableau.

    === "Gauche"
        Code:

        ```md
        | Firstname | Lastname | Age |
        |:----------|:---------|:----|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |
        ```

        Rendu:
        
        | Firstname | Lastname | Age |
        |:----------|:---------|:----|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |

    === "Centre"
        Code:

        ```md
        | Firstname | Lastname | Age |
        |:---------:|:--------:|:---:|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |
        ```

        Rendu:
        
        | Firstname | Lastname | Age |
        |:---------:|:--------:|:---:|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |

    === "Droite"
        Code:

        ```md
        | Firstname | Lastname | Age |
        |----------:|---------:|----:|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |
        ```

        Rendu:
        
        | Firstname | Lastname | Age |
        |----------:|---------:|----:|
        | Jill      | Smith    | 50  |
        | Eve       | Jackson  | 94  |
