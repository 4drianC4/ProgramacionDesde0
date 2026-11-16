---
tipo: recurso
tags: [java, recursos, glosario]
---

# Glosario

Términos de las clases 1 y 2, en orden alfabético. Entre paréntesis, la clase donde se explican.

| Término | Definición |
|---|---|
| **Acumulador** | Variable que empieza en un valor (normalmente 0) y va sumando otros valores: `s = s + x`. ([[Clase 01 - Apuntes\|C1]]) |
| **Algoritmo** | Secuencia finita y ordenada de pasos que resuelve un problema. ([[Clase 01 - Apuntes\|C1]]) |
| **Alcance (*scope*)** | Zona del código donde una variable existe: el bloque donde se declaró. ([[Clase 01 - Apuntes\|C1]]) |
| **Argumento** | Valor concreto que se pasa a un método al llamarlo: en `sumar(8, 8)` los argumentos son 8 y 8. ([[Clase 02 - Apuntes\|C2]]) |
| **Asignación** | Guardar un valor en una variable con `=`. La derecha se evalúa y se guarda en la izquierda. ([[Clase 01 - Apuntes\|C1]]) |
| **Atributo** | Variable declarada en la clase, fuera de los métodos. Representa una característica del objeto. También: campo, propiedad, variable de instancia. ([[Clase 01 - Apuntes\|C1]]) |
| **Bit / Byte** | Bit: un 0 o un 1. Byte: 8 bits. ([[Clase 01 - Apuntes\|C1]]) |
| **Bloque** | Código entre llaves `{ }`. ([[Clase 01 - Apuntes\|C1]]) |
| **BlueJ** | Entorno de desarrollo (IDE) para aprender Java que permite crear objetos y probar métodos visualmente. ([[Clase 01 - Apuntes\|C1]]) |
| **Bytecode** | Código intermedio (`.class`) que genera el compilador de Java y ejecuta la JVM. ([[Clase 01 - Apuntes\|C1]]) |
| ***Casting*** | Conversión explícita de un tipo a otro: `(int) 9.99` → `9`. ([[Clase 02 - Apuntes\|C2]]) |
| **Clase** | Molde que define los atributos y los métodos de un tipo de objeto. ([[Clase 01 - Apuntes\|C1]]) |
| **Compilar** | Revisar la sintaxis del código y traducirlo a bytecode. ([[Clase 01 - Apuntes\|C1]]) |
| **Concatenar** | Unir textos con `+`: `"Hola " + nombre`. ([[Clase 02 - Apuntes\|C2]]) |
| **Constante** | Variable cuyo valor no puede cambiar; se declara con `final`. ([[Clase 01 - Apuntes\|C1]]) |
| **Constructor** | Bloque especial con el mismo nombre que la clase y sin tipo de retorno; crea el objeto e inicializa sus atributos. ([[Clase 01 - Apuntes\|C1]]) |
| **Contador** | Variable que aumenta de uno en uno: `c = c + 1`. ([[Clase 01 - Apuntes\|C1]]) |
| **Cortocircuito** | En `a && b` o `a \|\| b`, Java no evalúa `b` si ya conoce el resultado con `a`. ([[Clase 02 - Apuntes\|C2]]) |
| **Declaración** | Indicar que una variable existe, con su tipo y nombre: `int edad;`. ([[Clase 01 - Apuntes\|C1]]) |
| **División entera** | División entre dos enteros: descarta la parte decimal (`7 / 2` → `3`). ([[Clase 02 - Apuntes\|C2]]) |
| **Error de lógica** | El programa compila pero da un resultado incorrecto. ([[Clase 01 - Apuntes\|C1]]) |
| **Error de sintaxis** | El código está mal escrito y no compila. ([[Clase 01 - Apuntes\|C1]]) |
| **Expresión** | Combinación de valores, variables y operadores que produce un valor. ([[Clase 02 - Apuntes\|C2]]) |
| **IDE** | Entorno de desarrollo: editor + compilador + herramientas (BlueJ, IntelliJ, NetBeans…). ([[Clase 01 - Apuntes\|C1]]) |
| **`if` / `else`** | Sentencia de control condicional: ejecuta un bloque u otro según una condición. ([[Clase 02 - Apuntes\|C2]]) |
| **Inicialización** | Dar el primer valor a una variable. ([[Clase 01 - Apuntes\|C1]]) |
| **JVM** | Máquina Virtual de Java: ejecuta el bytecode en cualquier sistema operativo. ([[Clase 01 - Apuntes\|C1]]) |
| **`main`** | Método `public static void main(String[] args)`: el punto de entrada de un programa Java. ([[Clase 02 - Apuntes\|C2]]) |
| **Método** | Acción que sabe hacer un objeto. Tiene acceso, tipo de retorno, nombre, parámetros y cuerpo. ([[Clase 02 - Apuntes\|C2]]) |
| **Módulo (`%`)** | Operador que devuelve el residuo de una división entera. ([[Clase 02 - Apuntes\|C2]]) |
| **Objeto** | Elemento concreto creado a partir de una clase, con sus propios valores. ([[Clase 01 - Apuntes\|C1]]) |
| **Operador ternario** | `condición ? a : b`: un `if-else` corto que devuelve un valor. ([[Clase 02 - Apuntes\|C2]]) |
| **Palabra reservada** | Palabra con significado fijo en Java (`class`, `int`, `if`…); no se puede usar como nombre. ([[Clase 01 - Apuntes\|C1]]) |
| **Parámetro** | Variable declarada entre los paréntesis de un método; recibe un dato desde afuera. ([[Clase 02 - Apuntes\|C2]]) |
| **Precedencia** | Orden en que se evalúan los operadores de una expresión. ([[Clase 02 - Apuntes\|C2]]) |
| **Prueba de escritorio** | Simulación a mano de un algoritmo, anotando paso a paso los valores de las variables. ([[Clase 01 - Apuntes\|C1]]) |
| **`return`** | Termina un método y entrega un valor a quien lo llamó. ([[Clase 02 - Apuntes\|C2]]) |
| **`Scanner`** | Clase de `java.util` para leer datos del teclado. ([[Clase 02 - Apuntes\|C2]]) |
| **`static`** | Indica que un atributo o un método pertenece a la clase, no a cada objeto. ([[Clase 02 - Apuntes\|C2]]) |
| **`String`** | Clase de Java que representa una cadena de caracteres. ([[Clase 01 - Apuntes\|C1]]) |
| **Tipo de dato** | Naturaleza del valor que guarda una variable (`int`, `double`, `char`…). ([[Clase 01 - Apuntes\|C1]]) |
| **Tipo primitivo** | Uno de los 8 tipos básicos: `byte`, `short`, `int`, `long`, `float`, `double`, `boolean`, `char`. ([[Clase 01 - Apuntes\|C1]]) |
| **Variable** | Espacio en memoria con un nombre que guarda un valor de un tipo. ([[Clase 01 - Apuntes\|C1]]) |
| **Variable local** | Variable declarada dentro de un método; muere al cerrarse su bloque. ([[Clase 01 - Apuntes\|C1]]) |
| **`void`** | Tipo de retorno de un método que no devuelve nada. ([[Clase 02 - Apuntes\|C2]]) |
