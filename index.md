
# Minando Codigo De Legacy a Legendario


¡Bienvenidos a esta exposición! Este es una mini reseña creada para todos los entusiastas de la tecnología y la programación, con un enfoque especial en aquellos que buscan la mejora continua y la excelencia en el software. Esta exposición es una demostración de cómo un proyecto heredado puede ser transformado en un código más limpio, eficiente y accesible, mediante la aplicación de principios y técnicas de la ingeniería de software moderna. Compartire con ustedes descubrimientos, desafíos y soluciones, con la intención de ofrecer una guía práctica y valiosa para aquellos que se enfrentan a desafíos similares.


## MinesweeperGame

daremos inicio a la aventura de transformar un proyecto legacy, específicamente un juego de Buscaminas, en un código más limpio y eficiente. Con las técnicas y herramientas adecuadas, un código antiguo y desordenado puede convertirse en un código moderno y de alta calidad.

En el contexto de la materia **“Calidad de Software y Gestión de Deuda Técnica”**, nos enfrentamos al desafío de mejorar este juego de Buscaminas que presentaba problemas comunes en el código antiguo. Aplicamos diversas técnicas y buenas prácticas, incluyendo la implementación de pruebas unitarias y la reestructuración del código, para hacerlo más legible, mantenible y escalable.

El resultado es un código más limpio y amigable que no sólo funciona de manera eficiente, sino que también es fácil de entender y modificar.

A continuación, compartire más detalles sobre este proceso y los desafíos que enfrente durante esta transformación. ¡Acompañame en este viaje y descubre cómo un viejo juego de Buscaminas puede convertirse en un ejemplo de código limpio y moderno!


> ![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/d60e2421-7e82-4cb7-98b9-23059238adf5)


  
### Code Smells

* Problema 1 (Falta de documentacion y pruebas)
  
![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/27a253a2-0afb-4cbb-98d3-194711930a1b)
   
![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/697aecc6-de10-4964-807b-0a5bde471078)

* Problema 2 (Clase Dios)
  > ~~FielValidator.cs~~
  
  ```C#
    public class FieldValidator : IFieldValidator
    {

        /// <summary>
        /// Checks if rows and cols choosed by user are valid.
        /// </summary>
        /// <param name="inputArgs">Input arguments</param>
        /// <returns>Array that holds the rows and colums or null if the input arguments are invalid.</returns> 
        public int[] checkRowsCols()
        {

            int[] rowsCols = null;

            int rows, cols;
            rows = cols = 0;

            // read the line from user input
            string inputLine = Console.ReadLine();

            // splits line on spaces
            string[] inputArgs = inputLine.Split(' ');

            // check null or length input arguments (the numbers must be two)
            if (inputArgs == null || inputArgs.Length != 2)
            {
                printMessage(MessageModel.INVALID_ARGUMENTS_NUMBER);
                printMessage(MessageModel.PRESS_ANY_KEY_TO_EXIT);
                Environment.Exit(0);
            }
        }
    }
  ```
  
* Problema 6 Manejo de errores
  > _Environment.Exit(0)_

![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/6ecbe80e-66e2-48b3-bdee-0f8de6310ae9)

  
* Problema 8 UI Expirience
  > _Console.ReadLine()_

![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/ed0f00e0-e2cd-40bb-8eac-088da92df748)

### Buenas practicas

| Lo Bueno        | Recomendaciones         |
|:-----------------|:------------------|
| Nombres significativos           | Integración continua (IC) |
| Funciones | Tratamiento de errores  |
| Formato            | DRY (Don't Repeat Yourself)   |
| Simplicidad del código           | Implementar Interfaz |

* * *

### Lo mejor de este proyecto
* GitHub Pages
   
   ![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/ad4e2daf-f23d-4ead-94d3-6b333a0d66c5)

* CI

  ![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/46273a49-0b57-4659-88c1-52fdeae08be1)

  ![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/31548fc9-1747-4aa8-a815-36493d8bb7b9)

* Entendimiento de las buenas practicas

   ![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/ecaadd93-fba1-4fd7-a964-422ce4364233)
