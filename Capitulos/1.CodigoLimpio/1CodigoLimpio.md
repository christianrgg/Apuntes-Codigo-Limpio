__INTRODUCCIÓN__

*Principios de la filosofia 5S
    __1. Seiri u organización:__ Saber donde estan las cosas mediante enfoques como el uso de nombres correctos. 
    __2. Seiton o sistematización:__ Un fragmento de codigo debe estar donde esperamos encontrarlo, caso contrario  refactorizar hasta conseguirlo. 
    __3. Seiso o limpieza:__ Mantenga limpio el lugar de trabajo, no indundar el codigo de comentarios e historias para el futuro.
    __4. Seiketsu o estandarización:__ El grupo decide como mantener limpio el lugar de trabajo. 
    __5.Shutsuke o diciplina:__ Ser diciplinado en la aplicación de prácticas, reflejarlas en el trabajo y aceptar los cambios. 

Al igual que mantenemos coches y otras máquinas, __En el código, debemos refactorizar sin compasión__
__Ley de LeBlanc:Después es igual a nunca__ 

__1 CODIGO LIMPIO__

*Hagase el codigo
El código es básicamente el lenguaje en el que expresamos los requisitos en última instancia.

*Codigo Incorrecto
Comercialiar productos antes de tiempo con graves fallos en el código provoca que al añadir nuevas funciones, el código empeoré hasta que ya no se pueda controlar. El código incorrecto es el motivo del fin de cualquier empresa de software.

*Coste total de un desastre
Cada cambio en el código afecta a dos o tres partes del mismo. Ningún cambio es trivial. Para ampliar o modificar el sistema es necesario comprender todos los detalles, efectos y
consecuencias, para de ese modo poder añadir nuevos detalles, efectos y consecuencias. Con el tiempo, el desastre aumenta de tal modo que no se puede remediar. Es imposible. Al aumentar este desastre, la productividad del equipo disminuye y acaba por desaparecer. Si se forma un nuevo equipo, el nuevo equipo no conocerá los detalles por lo que en lugar de mejorar la productividad esta tenderá a 0. 

*El gran cambio del diseño
Ahora los dos equipos compiten. El nuevo debe crear un sistema que haga lo que el antiguo no puede. Además, deben asumir los cambios que continuamente se aplican al sistema antiguo. La dirección no sustituirá el sistema antiguo hasta que el nuevo sea capaz de hacer todo lo que hace el antiguo. Con el tiempo los integrantes nuevos se van y los viejos exigen un nuevo cambio de diseño y ciclo se repite. __Dedicar tiempo a que el código sea correcto no sólo es rentable, es una cuestión de supervivencia profesional__

*Actitud 
Muchos quieren código correcto, aunque estén obsesionados con los objetivos. Pueden defender apasionadamente los objetivos y los requisitos, pero es su trabajo. El nuestro es defender el código con la misma intensidad.

*El enigma
La única forma de resolverlo, de cumplirlo, de avanzar, es intentar que el código siempre sea limpio.

*¿El arte del código limpio?
Reconocer código limpio no significa que sepamos cómo crearlo.
Para crearlo se requiere el uso disciplinado de miles de técnicas aplicadas mediante un detallado sentido de la «corrección». Este sentido del código es la clave.
Un programador que cree código limpio es un artista que puede transformar un lienzo en blanco en un sistema de código elegante.

*Concepto de código limpio
-La lógica debe ser directa para evitar errores ocultos 
-Las dependencias deben ser mínimas para facilitar el mantenimiento,
-El procesamiento de errores completo y sujeto a una estrategia articulada, 
-El rendimiento debe ser óptimo para que los usuarios no tiendan a estropear el código
-El código incorrecto tiende a aumentar el desastre. Cuando otros corrigen u optimizan código incorrecto, tienden a empeorarlo.
-El código limpio se lee como un texto bien escrito, como una novela. 
-El código debe ser culto en función del lenguaje, ya que no toda la información necesaria se puede expresar de forma clara en el código.
-El código, sin pruebas, no es limpio.
-Cuanto más pequeño, mejor.
-El código limpio es aquél al que se le ha dado importancia. Alguien ha dedicado su tiempo para que sea sencillo y ha prestado atención a los detalles.
-Ejecuta todas las pruebas.
-No contiene duplicados.
-Expresa todos los conceptos de diseño del sistema.
-Minimiza el número de entidades como clases, métodos,funciones y similares.

*Somos autores
La proporción entre tiempo dedicado a leer frente a tiempo dedicado a escribir es de más de 10:1.Al ser una proporción tan elevada, queremos que la lectura del código sea sencilla, aunque eso complique su creación.

*La regla del Boy Scout
Dejar el campamento más limpio de lo que se ha encontrado: No hace falta que la limpieza sea masiva. Cambie el nombre de una variable, divida una función demasiado extensa, elimine elementos duplicados, simplifique una instrucción if compuesta.

*Precuela y principios
-Principios de diseño como SRP: Single Responsibility Principle o Principio de
responsabilidad única
-OCP: Open Closed Principle o Principio Abierto/Cerrado
-





