---
tipo: recurso
tags: [java, recursos, glosario]
---

# Glosario

Términos del curso, en orden alfabético. Entre paréntesis, el día donde se explican.

| Término | Definición |
|---|---|
| **Acumulador** | Variable que empieza en un valor (normalmente 0) y va sumando otros valores: `s = s + x`. ([[Día 01 - Apuntes\|Día 1]]) |
| **Alcance (*scope*)** | Zona del código donde una variable existe: el bloque donde se declaró. ([[Día 02 - Apuntes\|Día 2]]) |
| **Algoritmo** | Secuencia finita y ordenada de pasos que resuelve un problema. ([[Día 01 - Apuntes\|Día 1]]) |
| **Argumento** | Valor concreto que se pasa a un método al llamarlo: en `sumar(8, 8)` los argumentos son 8 y 8. ([[Día 04 - Apuntes\|Día 4]]) |
| **Arreglo** | Estructura que guarda muchos valores del mismo tipo bajo un nombre, accesibles por su índice: `int[] a = new int[5];`. ([[Día 09 - Apuntes\|Día 9]]) |
| **Arreglos paralelos** | Varios arreglos del mismo tamaño donde la misma posición corresponde al mismo elemento. ([[Día 09 - Apuntes\|Día 9]]) |
| **Asignación** | Guardar un valor en una variable: `edad = 20`. La derecha se evalúa y se guarda en la izquierda. ([[Día 01 - Apuntes\|Día 1]]) |
| **Atributo** | Variable declarada en la clase, fuera de los métodos. Representa una característica del objeto. También: campo, propiedad, variable de instancia. ([[Día 02 - Apuntes\|Día 2]]) |
| **Bandera** | Variable `boolean` que recuerda si algo ocurrió durante un ciclo. ([[Día 06 - Apuntes\|Día 6]]) |
| **Bit / Byte** | Bit: un 0 o un 1. Byte: 8 bits. ([[Día 01 - Apuntes\|Día 1]]) |
| **Bloque** | Código entre llaves `{ }`. ([[Día 02 - Apuntes\|Día 2]]) |
| **BlueJ** | Entorno de desarrollo (IDE) para aprender Java que permite crear objetos y probar métodos visualmente. ([[Día 02 - Apuntes\|Día 2]]) |
| **`break` / `continue`** | `break` sale del ciclo (o del `switch`); `continue` salta a la siguiente vuelta. ([[Día 07 - Apuntes\|Día 7]]) |
| **Burbuja** | Método de ordenamiento que compara elementos vecinos y los intercambia si están en el orden incorrecto. ([[Día 09 - Apuntes\|Día 9]]) |
| **Bytecode** | Código intermedio (`.class`) que genera el compilador de Java y ejecuta la JVM. ([[Día 01 - Apuntes\|Día 1]]) |
| ***Casting*** | Conversión explícita de un tipo a otro: `(int) 9.99` → `9`. ([[Día 03 - Apuntes\|Día 3]]) |
| **Centinela** | Valor especial que indica el fin de una serie de datos (por ejemplo, ingresar 0 para terminar). ([[Día 06 - Apuntes\|Día 6]]) |
| **Ciclo (bucle)** | Estructura que repite un bloque de instrucciones: `while`, `do-while`, `for`. ([[Día 06 - Apuntes\|Día 6]]) |
| **Ciclo infinito** | Ciclo cuya condición nunca se vuelve falsa, por lo que no termina. ([[Día 06 - Apuntes\|Día 6]]) |
| **Ciclos anidados** | Un ciclo dentro de otro; el interno se ejecuta completo por cada vuelta del externo. ([[Día 07 - Apuntes\|Día 7]]) |
| **Clase** | Molde que define los atributos y los métodos de un tipo de objeto. ([[Día 02 - Apuntes\|Día 2]]) |
| **Compilar** | Revisar la sintaxis del código y traducirlo a bytecode. ([[Día 01 - Apuntes\|Día 1]]) |
| **Concatenar** | Unir textos con `+`: `"Hola " + nombre`. ([[Día 03 - Apuntes\|Día 3]]) |
| **Constante** | Variable cuyo valor no puede cambiar; se declara con `final`. ([[Día 02 - Apuntes\|Día 2]]) |
| **Constructor** | Bloque especial con el mismo nombre que la clase y sin tipo de retorno; crea el objeto e inicializa sus atributos. ([[Día 02 - Apuntes\|Día 2]]) |
| **Contador** | Variable que aumenta de uno en uno: `c = c + 1`. ([[Día 01 - Apuntes\|Día 1]]) |
| **Cortocircuito** | En `a && b` o `a \|\| b`, Java no evalúa `b` si ya conoce el resultado con `a`. ([[Día 03 - Apuntes\|Día 3]]) |
| **Declaración** | Indicar que una variable existe, con su tipo y nombre: `int edad;`. ([[Día 02 - Apuntes\|Día 2]]) |
| **Diagonal principal / secundaria** | En una matriz cuadrada, las casillas con `f == c` / con `f + c == n - 1`. ([[Día 10 - Apuntes\|Día 10]]) |
| **División entera** | División entre dos enteros: descarta la parte decimal (`7 / 2` → `3`). ([[Día 03 - Apuntes\|Día 3]]) |
| **`do-while`** | Ciclo que ejecuta el cuerpo y después revisa la condición; se ejecuta al menos una vez. ([[Día 06 - Apuntes\|Día 6]]) |
| **Error de lógica** | El programa compila pero da un resultado incorrecto. ([[Día 01 - Apuntes\|Día 1]]) |
| **Error de sintaxis** | El código está mal escrito y no compila. ([[Día 01 - Apuntes\|Día 1]]) |
| **Expresión** | Combinación de valores, variables y operadores que produce un valor. ([[Día 03 - Apuntes\|Día 3]]) |
| **`for`** | Ciclo que reúne inicialización, condición y actualización en una línea; ideal cuando se sabe cuántas veces repetir. ([[Día 07 - Apuntes\|Día 7]]) |
| **`for-each`** | Forma del `for` para recorrer todos los elementos de un arreglo: `for (int x : a)`. ([[Día 09 - Apuntes\|Día 9]]) |
| **IDE** | Entorno de desarrollo: editor + compilador + herramientas (BlueJ, IntelliJ, NetBeans…). ([[Día 02 - Apuntes\|Día 2]]) |
| **`if` / `else`** | Sentencia de control condicional: ejecuta un bloque u otro según una condición. ([[Día 05 - Apuntes\|Día 5]]) |
| **Índice** | Posición de un elemento en una cadena, un arreglo o una matriz; empieza en 0. ([[Día 08 - Apuntes\|Día 8]]) |
| **Inicialización** | Dar el primer valor a una variable. ([[Día 02 - Apuntes\|Día 2]]) |
| **Inmutable** | Que no puede cambiar. Los `String` son inmutables: sus métodos devuelven cadenas nuevas. ([[Día 08 - Apuntes\|Día 8]]) |
| **JVM** | Máquina Virtual de Java: ejecuta el bytecode en cualquier sistema operativo. ([[Día 01 - Apuntes\|Día 1]]) |
| **`main`** | Método `public static void main(String[] args)`: el punto de entrada de un programa Java. ([[Día 04 - Apuntes\|Día 4]]) |
| **Matriz** | Arreglo de dos dimensiones, organizado en filas y columnas: `m[f][c]`. ([[Día 10 - Apuntes\|Día 10]]) |
| **Método** | Acción que sabe hacer un objeto. Puede recibir parámetros y devolver un valor. ([[Día 02 - Apuntes\|Día 2]]) |
| **Módulo (`%`)** | Operador que devuelve el residuo de una división entera. ([[Día 03 - Apuntes\|Día 3]]) |
| **Objeto** | Elemento concreto creado a partir de una clase, con sus propios valores. ([[Día 02 - Apuntes\|Día 2]]) |
| **Operador ternario** | `condición ? a : b`: un `if-else` corto que devuelve un valor. ([[Día 05 - Apuntes\|Día 5]]) |
| **Palabra reservada** | Palabra con significado fijo en Java (`class`, `int`, `if`…); no se puede usar como nombre. ([[Día 02 - Apuntes\|Día 2]]) |
| **Parámetro** | Variable declarada entre los paréntesis de un método; recibe un dato desde afuera. ([[Día 02 - Apuntes\|Día 2]]) |
| **Precedencia** | Orden en que se evalúan los operadores de una expresión. ([[Día 03 - Apuntes\|Día 3]]) |
| **Prueba de escritorio** | Simulación a mano de un algoritmo, anotando paso a paso los valores de las variables. ([[Día 01 - Apuntes\|Día 1]]) |
| **Referencia** | Lo que recibe un método cuando se le pasa un arreglo u objeto: el mismo dato, no una copia. ([[Día 09 - Apuntes\|Día 9]]) |
| **`return`** | Termina un método y entrega un valor a quien lo llamó. ([[Día 02 - Apuntes\|Día 2]]) |
| **`Scanner`** | Clase de `java.util` para leer datos del teclado. ([[Día 04 - Apuntes\|Día 4]]) |
| **`static`** | Indica que un atributo o un método pertenece a la clase, no a cada objeto. ([[Día 04 - Apuntes\|Día 4]]) |
| **`String`** | Clase de Java que representa una cadena de caracteres. ([[Día 02 - Apuntes\|Día 2]]) |
| **`switch`** | Sentencia que elige un bloque según el valor exacto de una variable (`case`, `break`, `default`). ([[Día 05 - Apuntes\|Día 5]]) |
| **`this`** | Referencia al objeto actual; distingue un atributo de un parámetro con el mismo nombre. ([[Día 10 - Apuntes\|Día 10]]) |
| **Tipo de dato** | Naturaleza del valor que guarda una variable (`int`, `double`, `char`…). ([[Día 02 - Apuntes\|Día 2]]) |
| **Tipo primitivo** | Uno de los 8 tipos básicos: `byte`, `short`, `int`, `long`, `float`, `double`, `boolean`, `char`. ([[Día 02 - Apuntes\|Día 2]]) |
| **Variable** | Espacio en memoria con un nombre que guarda un valor de un tipo. ([[Día 02 - Apuntes\|Día 2]]) |
| **Variable local** | Variable declarada dentro de un método; muere al cerrarse su bloque. ([[Día 02 - Apuntes\|Día 2]]) |
| **`void`** | Tipo de retorno de un método que no devuelve nada. ([[Día 04 - Apuntes\|Día 4]]) |
| **`while`** | Ciclo que repite un bloque mientras la condición sea verdadera; puede ejecutarse 0 veces. ([[Día 06 - Apuntes\|Día 6]]) |
