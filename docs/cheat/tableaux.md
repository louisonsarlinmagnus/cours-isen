# Tableaux

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
