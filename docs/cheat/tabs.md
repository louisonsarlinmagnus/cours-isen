# Tabs

Il est possible de créer des blocs contenant des onglets.

!!! warning "Indentation"
    Faire très attention a l'indentation dans ces blocs!

=== "Code"
    ```
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


!!! info "Explications"
    `===` permet de définir un nouvel onglet