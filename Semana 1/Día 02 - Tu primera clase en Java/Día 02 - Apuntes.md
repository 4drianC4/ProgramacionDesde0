---
tipo: apuntes
dia: 2
semana: 1
tema: Tu primera clase en Java
tags: [java, intro-programacion, dia-02, apuntes]
---

# Día 2 · Tu primera clase en Java

> [!info] Datos de la clase
> **Semana 1 · Martes** · **IDE:** BlueJ · **Requisito:** [[Día 01 - Apuntes|Día 1]]
> **Material del día:** [[Día 02 - Diapositivas|Diapositivas]] · [[Día 02 - Práctica|Práctica]] · [[README|Ruta de aprendizaje]]

> [!abstract] Al terminar este día podrás…
> - Instalar BlueJ y crear un proyecto.
> - Reconocer las partes de una **clase en Java** (atributos, constructor y métodos) y probarla creando objetos.
> - Elegir el **tipo de dato** correcto para cada valor.
> - Declarar, inicializar y usar **variables** y **constantes**, respetando su **alcance**.

---

### 1. Preparar el entorno con BlueJ

Usaremos **BlueJ** porque deja **ver** los objetos y probar métodos sin escribir código extra.

1. Descarga BlueJ desde <https://www.bluej.org/> (ya trae su propio JDK de Java incluido).
2. Instálalo y ábrelo.
3. **Proyecto → Nuevo proyecto**. Crea una carpeta para el curso y un proyecto por tema (por ejemplo `Clase01`).
4. **Nueva clase** → escribe el nombre (empieza con **mayúscula**) → doble clic para abrir el editor.

> [!tip] Si usas otro IDE
> IntelliJ, NetBeans, Eclipse o VS Code también sirven. La lógica es la misma; solo cambia que para probar necesitarás un método `main` (lo veremos el [[Día 04 - Apuntes|Día 4]]).

### 2. Clase y objeto

- Una **clase** es un **molde**: define de forma general qué **tiene** (propiedades) y qué **hace** (comportamiento) algo.
- Un **objeto** es una cosa concreta creada a partir del molde, con **sus propios valores**.

> [!example] Clase `Auto` → objetos
> Todo auto tiene **color** y **marca** (eso lo dice la clase). Pero *mi* auto es rojo y Toyota, y el *tuyo* es azul y Nissan (esos son objetos). Ambos nacieron del mismo molde.

### 3. Estructura de una clase

Cuando creas una clase en BlueJ, aparece una plantilla como esta (traducida):

```java
/**
 * Escribe aquí una descripción de la clase Ejemplo.
 */
public class Ejemplo {
    // 1) ATRIBUTOS (variables de instancia)
    private int x;

    // 2) CONSTRUCTOR: crea objetos y da valores iniciales
    public Ejemplo() {
        x = 0;
    }

    // 3) MÉTODOS: lo que el objeto sabe hacer
    /**
     * Un ejemplo de método.
     * @param y  un parámetro de ejemplo
     * @return   la suma de x más y
     */
    public int metodoEjemplo(int y) {
        return x + y;
    }
}
```

| Parte | Para qué sirve |
|---|---|
| `public class Ejemplo { … }` | Declara la clase. Todo lo demás vive **dentro** de sus llaves |
| **Atributos** | Las características de cada objeto (también llamados *campos*, *propiedades* o *variables de instancia*) |
| **Constructor** | Tiene el **mismo nombre que la clase** y **no** tiene tipo de retorno. Su único trabajo es crear el objeto e **inicializar** los atributos |
| **Métodos** | Las acciones. Pueden recibir datos (**parámetros**) y devolver un resultado (`return`) |

**Bloques:** cada par de llaves `{ }` abre un **bloque**. Hay un bloque de la clase, uno del constructor y uno por cada método.

**Palabras reservadas:** las que BlueJ pinta de otro color (`public`, `class`, `int`, `return`…). Tienen un significado fijo y **no** puedes usarlas como nombres.

**Comentarios:**

```java
// comentario de una línea
/* comentario
   de varias líneas */
/** comentario de documentación (Javadoc):
    BlueJ lo muestra en la vista de documentación (Ctrl+J) */
```

### 4. Probar en BlueJ con objetos e inspector

1. **Compilar** (botón *Compile*). Si hay errores, BlueJ marca la línea.
2. Clic derecho sobre la clase → `new Ejemplo()` → ponle un nombre (`objeto1`). Aparece una ficha roja abajo: **ese es tu objeto**.
3. Doble clic sobre el objeto → **Inspector**: ves el **estado** (los valores de sus atributos).
4. Clic derecho sobre el objeto → elige un **método** → si pide parámetros, escríbelos → BlueJ muestra el **valor devuelto**.

> [!warning] Devolver ≠ imprimir
> Cuando un método hace `return`, **entrega** un valor que otro código puede usar. Imprimir (`System.out.println`) solo lo **muestra** en pantalla. No es lo mismo.

### 5. Tipos de datos

Cada variable tiene un **tipo** que indica la naturaleza del valor que guarda.

#### Primitivos numéricos enteros

| Tipo | Bits | Rango | Uso típico |
|---|---|---|---|
| `byte` | 8 | −128 a 127 | Datos muy pequeños |
| `short` | 16 | −32 768 a 32 767 | Poco usado |
| **`int`** | 32 | −2 147 483 648 a 2 147 483 647 | **El entero por defecto** |
| `long` | 64 | ≈ ±9,2 × 10¹⁸ | Números enormes. Requiere sufijo `L` |

#### Primitivos numéricos con decimales

| Tipo | Bits | Nota |
|---|---|---|
| `float` | 32 | Precisión simple. Requiere sufijo `F`: `4.5F` |
| **`double`** | 64 | **El decimal por defecto**. Sufijo `D` opcional |

#### Otros primitivos

| Tipo | Guarda | Literal |
|---|---|---|
| `boolean` | `true` o `false` | `boolean esValido = true;` |
| `char` | **un** carácter (letra, dígito, símbolo) | Comillas **simples**: `'D'` |

#### `String`: el tipo no primitivo que más usarás

```java
String nombre = "Merlín";      // comillas DOBLES
```

`String` **no** es primitivo: es una **clase** que Java ya trae (por eso no se pinta como las palabras reservadas y empieza con mayúscula). Una cadena es una secuencia de `char`.

```java
byte   edad      = 20;
short  anio      = 1998;
int    codigo    = 202_400_123;     // los "_" solo ayudan a leer
long   poblacion = 8_000_000_000L;  // sin la L: "integer number too large"
float  tiempo    = 4.5F;            // sin la F: "possible lossy conversion"
double medida    = 1234.5678;
boolean aprobado = true;
char   inicial   = 'D';
String carrera   = "Ing. de Sistemas";
```

> [!warning] Errores típicos del compilador
> - `byte b = 288;` → *incompatible types: possible lossy conversion from int to byte* (no cabe).
> - `long x = 9000000000;` → *integer number too large* (falta la `L`).
> - `float f = 4.5;` → *possible lossy conversion from double to float* (falta la `F`).
> - `char c = D;` → *cannot find symbol* (faltan las comillas simples).

#### `char` es, por dentro, un número

Cada carácter tiene un código numérico (tabla **ASCII**/Unicode). Java permite usarlos indistintamente:

| Carácter | Código |
|---|---|
| `'0'` … `'9'` | 48 … 57 |
| `'A'` … `'Z'` | 65 … 90 |
| `'a'` … `'z'` | 97 … 122 |

```java
char letra = 68;          // guarda 'D'
char h = 'h', a = 'a';
System.out.println(h - a);       // 7  (resta de códigos)
System.out.println((char) 112);  // p
```

> [!tip] Esto sale en exámenes
> El **cifrado César** se resuelve justamente con esta idea: las letras son números y se pueden sumar, restar y volver a convertir a `char`.

#### Curiosidades útiles para leer código ajeno

```java
int millon = 1_000_000;  // separador visual
int hex    = 0x1A;       // 26 en hexadecimal
int bin    = 0b11010;    // 26 en binario
```

### 6. Variables

Una **variable** es un **espacio en memoria con nombre** (identificador) que guarda un valor de un tipo.

```java
int edad;          // DECLARACIÓN: "va a existir edad"
edad = 20;         // ASIGNACIÓN: guarda 20
int nota = 75;     // DECLARACIÓN + INICIALIZACIÓN en una línea
int dia = 24, mes = 3;   // varias del mismo tipo en una línea
```

En `edad = 20`, el signo igual es el **operador de asignación**: lo de la **derecha** se guarda en la **izquierda**. No significa "igual": para comparar se usa `edad == 20` (lo veremos el [[Día 03 - Apuntes|Día 3]]).

#### Reglas y convenciones de nombres

| Regla (si no la cumples, no compila) | Convención (compila, pero no es correcto) |
|---|---|
| Letras, dígitos, `_` y `$` | Variables y métodos en `camelCase`: `notaFinal` |
| No puede empezar con un dígito | Clases en `PascalCase`: `CuentaBancaria` |
| No puede ser una palabra reservada | Constantes en `MAYUSCULAS`: `NOTA_MINIMA` |
| Distingue mayúsculas: `nota` ≠ `Nota` | Nombres que digan lo que guardan: `precio`, no `p` |

#### Alcance (*scope*)

Una variable **solo existe dentro del bloque donde se declaró** (y en los bloques que están dentro de él).

```java
public class Alcance {
    private int suma;            // atributo: visible en TODA la clase

    public void calcular(int a) { // a: parámetro, vive en el método
        int resta = a - 1;        // variable local, vive en el método
        suma = a + 1;             // ✔ puedo usar el atributo aquí
    }

    public int otro() {
        return resta;             // ✘ ERROR: resta no existe aquí
    }
}
```

| Tipo de variable | Dónde se declara | Cuánto vive |
|---|---|---|
| **Atributo** (de instancia, campo, *field*) | En la clase, fuera de los métodos | Lo que vive el objeto |
| **Parámetro** | Entre los paréntesis de un método | Lo que dura la llamada al método |
| **Local** (temporal) | Dentro de un método | Hasta que se cierra su bloque |

> [!warning] Locales sin valor
> Los **atributos** reciben un valor por defecto (`0`, `0.0`, `false`, `null`). Las **variables locales no**: si usas una sin inicializar, el compilador te avisa *variable might not have been initialized*.

#### Constantes

Si un valor **no debe cambiar**, se antepone `final`:

```java
final double GRAVEDAD = 9.8;
GRAVEDAD = 10;   // ✘ ERROR: cannot assign a value to final variable
```

### 7. Del pseudocódigo a Java

| Pseudocódigo | Java |
|---|---|
| `S ← 0` | `int s = 0;` |
| `C ← C + 1` | `c = c + 1;` |
| `M ← A` | `m = a;` |
| `Mostrar S` | `System.out.println(s);` |
| `Leer X` | `x = sc.nextInt();` (lo veremos el [[Día 04 - Apuntes\|Día 4]]) |

> [!example] Una clase completa con lo de esta clase
> ```java
> public class Estudiante {
>     private String nombre;
>     private int nota1;
>     private int nota2;
>     private final int NOTA_MINIMA = 51;
>
>     public Estudiante() {
>         nombre = "Sin nombre";
>         nota1 = 0;
>         nota2 = 0;
>     }
>
>     public int getNotaMinima() {
>         return NOTA_MINIMA;
>     }
> }
> ```
> Compílala, crea un objeto e inspecciónalo: verás `nombre`, `nota1` y `nota2` con sus valores iniciales.

---

## Resumen

> [!summary] Lo esencial del Día 2
> - Una clase tiene **atributos + constructor + métodos**. Un objeto es una copia concreta de la clase.
> - En BlueJ: compilar → crear objeto → inspeccionar → ejecutar métodos.
> - Tipos por defecto: **`int`** para enteros, **`double`** para decimales. `long` lleva `L` y `float` lleva `F`. `char` va con `'…'`, `String` con `"…"`.
> - Una variable es un espacio en memoria con nombre. Vive **solo en su bloque**. `final` la vuelve constante.

## Siguiente paso

- ✍️ Practica: [[Día 02 - Práctica]]
- 📖 Glosario: [[Glosario]]
- ⬅️ Ayer: [[Día 01 - Apuntes|Día 1 · La computadora y los algoritmos]]
- ➡️ Mañana: [[Día 03 - Apuntes|Día 3 · Operadores y expresiones]]
