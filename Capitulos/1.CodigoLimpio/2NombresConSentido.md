__Introducción__
Los nombres son omnipresentes. Aparecen en variables,funciones, argumentos, clases y paquetes.
Elegir nombres correctos lleva tiempo, pero también ahorra trabajo.

El nombre de una variable, función o clase debe responder una serie de cuestiones básicas. Debe indicar por qué existe, qué hace y cómo se usa. Si un nombre requiere un comentario, significa que no revela su cometido.
    ###ERROR
        int d; // tiempo transcurrido en días


Debe elegir un nombre que especifique lo que se mide y la unidad de dicha medida:
    Ejemplo
        int elapsedTimeInDays;
        int daysSinceCreation;
        int daysSinceModification;
        int fileAgeInDays;

Para entender el siguiente codigo se necesita saber: ¿Qué contiene theList?, ¿Qué significado tiene el subíndice cero de un elemento de theList?, ¿Qué importancia tiene el valor 4?, ¿Cómo se usa la lista devuelta?. 

    public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList)
    if (x[0] == 4)
    list1.add(x);
    return list1;
    }

Las respuestas a estas preguntas no se encuentran en el código, pero se podrían haber incluido. 
El tablero es una lista de celdas llamada theList. Cambiemos el nombre por "gameBoard". Cada celda del teclado se representa por medio de una matriz. El subíndice cero es la ubicación de un valor de estado que, cuando es 4,
significa que se ha detectado. Al asignar nombres a estos conceptos mejoramos considerablemente el código:

    public List<int[]> getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard)
    if (cell[STATUS_VALUE] == FLAGGED)
    flaggedCells.add(cell);
    return flaggedCells;
    }

La simplicidad del código no ha cambiado. Sigue teniendo los mismos operadores y constantes y el mismo número de niveles anidados, pero ahora es mucho más explícito. Podemos crear una sencilla clase para celdas en lugar de usar una matriz de elementos int. Puede incluir una función que revele el objetivo (con el nombre isFlagged) para ocultar los números. El resultado es una nueva versión de la función:

    public List<Cell> getFlaggedCells() {
    List<Cell> flaggedCells = new ArrayList<Cell>();
    for (Cell cell : gameBoard)
    if (cell.isFlagged())
    flaggedCells.add(cell);
    return flaggedCells;
    }

__EN JAVASCRIPT SERI EL SIGUIENTE CODIGO__
function getFleggedCells() {
    const flaggedCells = [];
    if(let i = 0; i < gameBoard.length; i++) {
        cons cell = gameBoard[i];
        if (cell.isFlagged()){
            flaggedCells.push(cell);
        }
    }
    return flaggedCells;
}

__Evitar la desinformación__
-Debemos evitar palabras cuyo significado se aleje del que pretendemos. Por ejemplo, hp, aix y sco son nombres de variables pobres.
-No haga referencia a un grupo de cuentas como accountList a menos que realmente sea una lista (List).
-Evite usar nombres con variaciones mínimas: (a)XYZControllerForEfficientHandlingOfStrings; (b)XYZControllerForEfficientStorageOfStrings
-El uso de ortografía incoherente es desinformación 
-Un ejemplo de nombre desinformativo sería el uso de la L minúscula o la O mayúscula como nombres de variables, sobre todo combinados.
    int a = l;
    if ( O == l )
    a = O1;
    else
    l = 01;

__Realizar distinciones con sentido__
-Se crean problemas al crear código únicamente dirigido a un compilador o intérprete.
-Aunque se puede usar el mismo nombre para hacer referencia a dos elementos distintos en el mismo ámbito, puede verse tentado a cambiar un nombre de forma arbitraria. En ocasiones se hace escribiéndolo incorrectamente, lo que provoca que los errores ortográficos impidan la compilación.
-Los nombres de series numéricas (a1, a2… aN) simplemente no ofrecen información.
-Las palabras adicionales son otra distinción sin sentido. Si tiene otra clase con el nombre ProductInfo o
ProductData, habrá creado nombres distintos, pero con el mismo significado.
-No es incorrecto usar prefijos como a y the mientras la distinción tenga sentido.
-La palabra variable no debe incluirse nunca en el nombre de una variable. 
-La palabra table no debe incluirse nunca en el nombre de una tabla.


__Usar nombres que se puedan pronunciar__
-Cree nombres pronunciables. Si no lo puede pronunciar, no podrá explicarlo sin parecer tonto.
    --ERROR
        class DtaRcrd102 {
        private Date genymdhms;
        private Date modymdhms;
        private final String pszqint = “102”;
        /*… */
        };

    --MEJOR
        class Customer {
        private Date generationTimestamp;
        private Date modificationTimestamp;
        private final String recordId = “102”;
        /*… */
        };





































