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

__Usar nombres que se puedan buscar__
-Los nombres de una letra y las constantes numéricas tienen un problema: no son fáciles de localizar en el texto. Se puede detectar MAX_CLASSES_PER_STUDENT, pero el número 7 resulta más complicado.
-Nombres de una letra que sólo se puedan usar como variables locales dentro de métodos breves. La longitud de un nombre debe corresponderse al tamaño de su ámbito [N5]. Si una variable o constante se usa en varios puntos del código, debe asignarle un nombre que se pueda buscar.

Ejemplo con J: 
    for (int j=0; j<34; j++) {
    s += (t[j]*4)/5;
    }

__Evitar codificaciones__
Al codificar información de tipos o ámbitos en un nombre se dificulta la descodificación. No parece razonable que todos los nuevos empleados tengan que aprender otro lenguaje de codificación además del código con el
que van a trabajar.

__Notación húngara__
En la actualidad HN y otras formas de codificación de tipos no son más que un impedimento. Hacen que sea más complicado cambiar el nombre o el tipo de una variable o clase. Dificultan la legibilidad del código y pueden hacer que el sistema de codificación confunda al lector.

__Prefijos de miembros__
No necesario añadir m_ como prefijo a los nombres de variables. Lasvclases y funciones tienen el tamaño necesario para no tener que hacerlo, y debe usar un entorno de edición que resalte o coloree los miembros para
distinguirlos.

__Interfaces e Implementaciones__
Existe un caso especial para usar codificaciones. Imagine por ejemplo que crea una factoría abstracta para crear formas. Esta factoría será una interfaz y se implementará por medio de una clase concreta. ¿Qué nombres debe asignar? ¿IShapeFactory y ShapeFactory? La I inicial, tan habitual en los archivos de legado actuales es, en elmejor de los casos, una distracción, y en el peor, un exceso de información. Los usuarios no deben saber que se trata de una interfaz, Es mejor usar ShapeFactoryImp o incluso CShapeFactory, que codificar la interfaz.

__Evitar asignaciones mentales__
-Los lectores no tienen que traducir mentalmente sus nombres en otros que ya conocen.
-Un contador de bucles se podría bautizar como i, j o k (pero nunca l) si su ámbito es muy reducido y no hay conflictos con otros nombres, ya que los nombres de una letra son tradicionales en contadores de bucles.
-Si puede recordar que r es la versión en minúscula de una URL sin el host y el sistema, debe ser muy listo.
-Una diferencia entre un programador inteligente y un programador profesional es que este último sabe que la claridad es lo que importa. Los profesionales usan sus poderes para hacer el bien y crean código que otros
puedan entender.

__Nombres de clases__
-Las clases y los objetos deben tener nombres o frases de nombre como Customer, WikiPage, Account y AddressParser. 
-Evite palabras como Manager, Processor, Data, o Info en el nombre de una clase. 
El nombre de una clase no debe ser un verbo.

__Nombres de métodos__
Los métodos deben tener nombres de verbo como postPayment, deletePage o save. Los métodos de acceso, de modificación y los predicados deben tener como nombre su valor y usar como prefijo get, set e is de acuerdo al estándar de javabean.
EJEMPLO
    string name = employee.getName();
    customer.setName(“mike”);
    if (paycheck.isPosted())…

Al sobrecargar constructores, use métodos de factoría estáticos con nombres que describan los argumentos. Por ejemplo:
    Complex fulcrumPoint = Complex.FromRealNumber(23.0);
es mejor que:
    Complex fulcrumPoint = new Complex(23.0);

__No se exceda con el atractivo__
Opte por la claridad antes quepor el entretenimiento. En el código, el atractivo suele aparecer como formas
coloquiales o jergas. Por ejemplo, no use whack() en lugar de kill(). No recurra a bromas culturales como eatMyShorts() si quiere decir abort(). Diga lo que piense. Piense lo que diga.

__Una palabra por concepto__
Es importante utilizar una palabra consistente para cada operación similar en todas las clases. Por ejemplo, si quieres obtener la información de un empleado, en lugar de utilizar métodos diferentes como "getInfo" en la clase "Employee", "fetchData" en la clase "Department" y "retrieveEmployee" en la clase "Payroll", debes elegir una palabra como "get" y mantenerla en todos los métodos equivalentes. Por lo tanto, podrías tener métodos como "getInfo" en la clase "Employee", "getInfo" en la clase "Department" y "getEmployeeInfo" en la clase "Payroll". Esto hace que sea más fácil para ti y otros desarrolladores recordar y entender qué método se utiliza para obtener la información de un empleado en cualquier parte del código.

__No haga juegos de palabras__
-Evite usar la misma palabra con dos fines distintos.
-Nuestro objetivo, como autores, es facilitar la comprensión del código, no hacer un modelo académico que exija investigar el significado
mostrado.


    Imagina que tienes una caja donde guardas objetos. Ahora, tienes dos acciones diferentes que puedes realizar con esa caja:

    Agregar un objeto nuevo a la caja.
    1. Sumar o combinar dos objetos que ya están dentro de la caja.
    2. En este caso, "agregar" y "sumar/concatenar" son dos acciones diferentes que realizas con la caja.

    Ahora, piensa en cómo llamarías a los métodos que realizan estas acciones en tu programa:

    Si tienes un método llamado "add" que toma dos objetos dentro de la caja y los suma o concatena para obtener un nuevo objeto, eso está bien. Por ejemplo, puedes tener un método llamado "add" que toma dos números y los suma.

    Sin embargo, si quieres agregar un objeto nuevo a la caja, es mejor utilizar un nombre diferente para ese método. Por ejemplo, puedes llamarlo "insert" o "append". Esto ayuda a evitar confusiones, ya que el método "add" en este caso tiene un significado diferente y podría llevar a malentendidos si se utiliza para agregar objetos a la caja.

    La idea principal es utilizar nombres de métodos que reflejen claramente lo que están haciendo. Si dos métodos realizan acciones diferentes, aunque puedan ser similares en ciertos aspectos, es mejor utilizar nombres diferentes para evitar confusiones y hacer que el código sea más fácil de entender.

__Usar nombres de dominios de soluciones__
Los lectores de su código serán programadores. Por ello, use términos informáticos, algoritmos, nombres de patrones, términos matemáticos y demás. No conviene extraer todos los nombres del dominio de problemas ya que no queremos que nuestros colegas tengan que preguntar el significado de cada nombre en especial cuando ya conocen el concepto bajo otro nombre diferente.

__Usar nombres de dominios de problemas__
Cuando no exista un término de programación para lo que esté haciendo, use el nombre del dominio de problemas. Al menos el programador que mantenga su código podrá preguntar el significado a un experto en dominios.
EJEMPLO
    Supongamos que estás desarrollando un programa de gestión de inventario para una tienda de ropa. Necesitas escribir un método para realizar un descuento especial en ciertos productos de una categoría específica, digamos "camisetas".

    En este caso, no hay un término de programación específico para esta acción de descuento especial en camisetas. En lugar de elegir un nombre vago o confuso, es mejor usar un nombre que refleje el dominio del problema, en este caso, "aplicarDescuentoEspecialEnCamisetas".


__Añadir contexto con sentido__
Imagine que tiene las variables firstName, lastName, street, houseNumber, city, state y zipcode. Si las combina, es evidente que forman una dirección. Pero si la variable state se usa de forma aislada en un método, ¿sabría que forma parte de una dirección? Puede añadir contexto por medio de prefijos: addrFirstName, addrLastName, addrState, etc. Al menos los lectores comprenderán que estas variables forman parte de una estructura mayor. Evidentemente, es mejor crear la clase Address.
EJEMPLO DE CODIGO EN JAVASCRIPT
    class GuessStatisticsMessage {
    constructor() {
        this.number = "";
        this.verb = "";
        this.pluralModifier = "";
    }

    make(candidate, count) {
        this.createPluralDependentMessageParts(count);
        return `There ${this.verb} ${this.number} ${candidate}${this.pluralModifier}.`;
    }

    createPluralDependentMessageParts(count) {
        if (count === 0) {
        this.thereAreNoLetters();
        } else if (count === 1) {
        this.thereIsOneLetter();
        } else {
        this.thereAreManyLetters(count);
        }
    }

    thereAreManyLetters(count) {
        this.number = "1";
        this.verb = "is";
        this.pluralModifier = "";
    }

    thereIsOneLetter() {
        this.number = "1";
        this.verb = "is";
        this.pluralModifier = "";
    }

    thereAreNoLetters() {
        this.number = "no";
        this.verb = "are";
        this.pluralModifier = "s";
    }
    }

LOGICA: 
1. Se define la clase GuessStatisticsMessage con sus variables de instancia: number, verb y pluralModifier.
2. El método make recibe un candidato (candidate) y un contador (count). Llama al método createPluralDependentMessageParts para determinar los componentes del mensaje dependiendo del contador.
3. El método createPluralDependentMessageParts determina qué método de actualización de variables debe llamar en función del valor del contador.
4. Si el contador es igual a 0, se llama al método thereAreNoLetters, que actualiza las variables number, verb y pluralModifier para reflejar que no hay letras.
5. Si el contador es igual a 1, se llama al método thereIsOneLetter, que actualiza las variables number, verb y pluralModifier para reflejar que hay una letra.
6. Si el contador no es ni 0 ni 1, se llama al método thereAreManyLetters, que actualiza las variables number, verb y pluralModifier para reflejar que hay varias letras.
7. Cada uno de los métodos de actualización (thereAreNoLetters, thereIsOneLetter y thereAreManyLetters) asigna los valores adecuados a las variables number, verb y pluralModifier según el caso.
8. Finalmente, el método make utiliza las variables actualizadas para construir y devolver el mensaje completo.
Esta secuencia de ejecución garantiza que las variables number, verb y pluralModifier estén configuradas correctamente según el valor del contador, y el método make puede construir el mensaje final de acuerdo con esas variables.

__No añadir contextos innecesarios__
Los nombres breves suelen ser más adecuados que los extensos, siempre que sean claros. No añada más contexto del necesario a un nombre. Los nombres accountAddress y customerAddress son perfectos para instancias de la clase Address pero no sirven como nombres de clase. Address sirve como nombre de clase. Para distinguir entre direcciones MAC, direcciones de puertos y direcciones Web, podría usar PostalAddress, MAC y URI. Los nombres resultantes son más precisos, el objetivo de cualquier nombre.
EJEMPLO
    Imagina que estás desarrollando un programa para una biblioteca, y necesitas representar información sobre los libros prestados. Tienes una clase llamada Book que representa un libro en la biblioteca.

    Ahora, necesitas definir una variable para almacenar el estado de disponibilidad del libro, es decir, si está prestado o no. ¿Qué nombre sería más adecuado para esa variable: availabilityStatus o isAvailable?

    En este caso, el nombre más adecuado sería isAvailable. Aunque availabilityStatus podría ser más descriptivo, isAvailable es más corto, directo y sigue la convención de nombres booleanos en muchos lenguajes de programación. Al utilizar isAvailable, se entiende claramente que se refiere al estado de disponibilidad del libro, sin necesidad de añadir información adicional.








































