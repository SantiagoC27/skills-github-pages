
# Minando Codigo De Legacy a Legendario


¡Bienvenidos a nuestra exposición! Este es un foro creado para todos los entusiastas de la tecnología y la programación, con un enfoque especial en aquellos que buscan la mejora continua y la excelencia en el software. Esta exposición es una demostración de cómo un proyecto heredado puede ser transformado en un código más limpio, eficiente y accesible, mediante la aplicación de principios y técnicas de la ingeniería de software moderna. A través de nuestras presentaciones, compartiremos nuestros descubrimientos, desafíos y soluciones, con la intención de ofrecer una guía práctica y valiosa para aquellos que se enfrentan a desafíos similares.


## MinesweeperGame

daremos inicio a la aventura de transformar un proyecto legacy, específicamente un juego de Buscaminas, en un código más limpio y eficiente. Con las técnicas y herramientas adecuadas, un código antiguo y desordenado puede convertirse en un código moderno y de alta calidad.

En el contexto de la materia **“Calidad de Software y Gestión de Deuda Técnica”**, nos enfrentamos al desafío de mejorar este juego de Buscaminas que presentaba problemas comunes en el código antiguo. Aplicamos diversas técnicas y buenas prácticas, incluyendo la implementación de pruebas unitarias y la reestructuración del código, para hacerlo más legible, mantenible y escalable.

El resultado es un código más limpio y amigable que no sólo funciona de manera eficiente, sino que también es fácil de entender y modificar.

A continuación, compartire más detalles sobre este proceso y los desafíos que enfrente durante esta transformación. ¡Acompañame en este viaje y descubre cómo un viejo juego de Buscaminas puede convertirse en un ejemplo de código limpio y moderno!

<p align="center">
  <img src="https://github.com/SantiagoC27/skills-github-pages/assets/89257540/d60e2421-7e82-4cb7-98b9-23059238adf5" alt="Code1") />
</p>

![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/27a253a2-0afb-4cbb-98d3-194711930a1b)
  
### Code Smells

* Problema 1 (Falta de documentacion y pruebas)
  
   ```C#
     public class FieldModel : IFieldModel
      {
          private SquareModel[,] mineField { get; set; }
          private int rows { get; set; }
          private int cols { get; set; }
  
          private readonly SquareModel square = new SquareModel();
  
          /// <summary>
          /// Object Field
          /// </summary>
          /// <param name="rows">Total rows.</param>
          /// <param name="cols">Total cols.</param>
          /// <param name="squaresMatrix">Squares matrix.</param>
          public FieldModel(int rows, int cols, SquareModel[,] squaresMatrix)
          {
              this.Rows = rows;
              this.Cols = cols;
              this.mineField = squaresMatrix;
          }
       }
   ```
   
![image](https://github.com/SantiagoC27/skills-github-pages/assets/89257540/697aecc6-de10-4964-807b-0a5bde471078)

* Problema 2 (Clase Dios)
  > ~~FielValidator.cs~~
* Problema 3 Mejoras de rendimiento
  
  ```C#
    /// <summary>
    /// Counts the number of adjacent mines to a square and replace the dot character with this number. 
    /// </summary>
    /// <param name="row">Square row.</param>
    /// <param name="col">Square col.</param>
    /// <returns>The square value after replacing the dot characters</returns>
    public string adjacentsMines(int row, int col)
    {
        if (this.mineField[row, col].squareValue == this.square.dotValue)
        {
            int[] directionRow = { 1, 1, 1, 0, -1, -1, -1, 0 };
            int[] directionCol = { 1, 0, -1, -1, -1, 0, 1, 1 };
            int minesCounter = 0;

            for (int direction = 0; direction < directionRow.Length; direction++)
            {
                int newRow = directionRow[direction] + row;
                int newCol = directionCol[direction] + col;
                if (this.checkBounds(newRow, newCol))
                {
                    if (this.mineField[newRow, newCol].mineFound)
                    {
                        minesCounter++;
                    }
                }
            }

            if (this.mineField[row, col].squareValue != this.square.mineValue)
                this.mineField[row, col].squareValue = Convert.ToString(minesCounter);
        }
        return this.mineField[row, col].squareValue;
    }
  ```
* Problema 6 Manejo de errores
  > _Environment.Exit(0)_
* Problema 8 UI Expirience
  > _Console.ReadLine()_

### Buenas practicas

| Lo Bueno        | Recomendaciones         |
|:-----------------|:------------------|
| Nombres significativos           | Principio de Responsabilidad Única |
| Funciones | Tratamiento de errores  |
| Formato            | DRY (Don't Repeat Yourself)   |
| Simplicidad del código           | Implementar Interfaz |
