## SuperFences

!!! tip
    Une SuperFence est un SuperTabs dans un bloc d'alerte

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

