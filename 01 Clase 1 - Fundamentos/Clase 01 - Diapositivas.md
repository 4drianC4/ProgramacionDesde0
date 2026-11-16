---
tipo: diapositivas
clase: 1
semanas: [1, 2]
tags: [java, intro-programacion, clase-01, diapositivas]
theme: white
transition: slide
---

# Clase 1

## Del algoritmo a la primera clase en Java

**Programación desde 0** · Apoyo para Introducción a la Programación (INF-135) · UMSS

---

# Hoy vamos a…

1. Entender qué hace una computadora y por qué usa **binario**
2. Escribir **algoritmos** y comprobarlos con la **prueba de escritorio**
3. Conocer la estructura de una **clase en Java**
4. Usar **tipos de datos**, **variables** y **constantes**

Apuntes completos: [[Clase 01 - Apuntes]]

---

# Semana 1

Pensar como computadora

---

# ¿Qué hace una computadora?

**Entrada → Proceso → Salida**, y guarda datos en **memoria**.

| | Ejemplo |
|---|---|
| Entrada | Teclado, archivo |
| Proceso | CPU |
| Salida | Pantalla, archivo |
| Memoria | RAM: tus variables |

---

# Hardware y software

- **Hardware:** lo que se toca → CPU, RAM, disco, teclado
- **Software:** las instrucciones → sistema operativo, BlueJ, **tus programas**

Programar = escribir software que le dice al hardware qué hacer.

---

# ¿Por qué binario?

Un circuito solo distingue **dos estados**: hay corriente / no hay corriente → **1 / 0**

- 1 **bit** = un 0 o un 1
- 1 **byte** = 8 bits = 256 valores
- Con *n* bits: **2ⁿ** valores

`26` en decimal = `11010` en binario → 16 + 8 + 2

---

# Lenguajes de programación

| Nivel | Cómo se ve |
|---|---|
| Máquina | `10110000 01100001` |
| Ensamblador | `MOV AL, 61h` |
| **Alto nivel** | `int edad = 20;` |

Java es de **alto nivel**: hay que **traducirlo**.

---

# De tu código a la ejecución

**`Ejemplo.java`** → *compilar* → **`Ejemplo.class`** (bytecode) → **JVM** → cualquier sistema operativo

> [!important] Compilar
> Revisa que esté **bien escrito**. Que compile **no** significa que funcione bien: puede tener **errores de lógica**.

---

# ¿Qué es un algoritmo?

Una secuencia **finita** y **ordenada** de pasos que resuelve un problema.

Como una **receta de cocina**: pasos numerados, en orden, que terminan.

**Características:** finito · correcto · robusto · completo · eficiente

---

# Pasos para resolver un problema

1. **Análisis:** ¿qué tengo? ¿qué debo obtener?
2. **Diseño:** el algoritmo
3. **Prueba de escritorio:** simularlo a mano
4. **Codificación:** pasarlo a Java
5. **Prueba:** ejecutarlo con varios datos

---

# La memoria: un casillero

| Variable | Contenido |
|---|---|
| `S` | 100 |
| `C` | −1 |
| `SUMA` | *basura* |

> [!warning] La memoria no empieza limpia
> Siempre da un **valor inicial** antes de usar una variable.

---

# Elementos básicos

| Elemento | Pseudocódigo |
|---|---|
| Asignación | `Z ← Z + 3` |
| Contador | `C ← 0` … `C ← C + 1` |
| Acumulador | `S ← 0` … `S ← S + X` |
| Leer / Mostrar | `Leer X` · `Mostrar S` |
| Condicional | `Si A > B Entonces … Sino …` |
| Repetición | `Si C < 10 Entonces Ir a 3` |

---

# Ejemplo: sumar del 1 al 10

```text
1. C ← 0
2. S ← 0
3. C ← C + 1
4. S ← S + C
5. Si C < 10 Entonces Ir a 3
6. Mostrar "La suma es: ", S
7. FIN
```

`C` cuenta · `S` acumula · pasos 1–2 **una sola vez**

---

# Prueba de escritorio

Una columna por variable, un valor nuevo por paso:

| C | S | ¿C < 10? |
|---|---|---|
| 0 | 0 | |
| 1 | 1 | sí |
| 2 | 3 | sí |
| … | … | … |
| 10 | 55 | **no** → mostrar |

---

# ¿Con qué datos probar?

1. Datos **fáciles** → ¿funciona?
2. Datos que lo hagan **fallar** → cero, negativos, límites
3. **Un dato por cada caso** posible

Nota: ≥ 51 APROBADO · < 50 REPROBADO · 50–51 ESPECIAL → probar **70, 40 y 50.5**

---

# Semana 2

Tu primera clase en Java

---

# BlueJ

- Descarga: **bluej.org** (ya trae Java)
- **Proyecto → Nuevo proyecto** → `Clase01`
- **Nueva clase** → nombre con **Mayúscula**
- Doble clic → editor

Deja **ver** los objetos y probar métodos sin código extra.

---

# Clase y objeto

- **Clase:** el **molde**. Define qué **tiene** y qué **hace** algo.
- **Objeto:** una cosa **concreta** hecha con el molde.

> [!example] Auto
> La clase dice: todo auto tiene **color** y **marca**. Mi auto (rojo, Toyota) y el tuyo (azul, Nissan) son **objetos**.

---

# Estructura de una clase

```java
public class Ejemplo {
    private int x;              // 1) atributos

    public Ejemplo() {          // 2) constructor
        x = 0;
    }

    public int sumar(int y) {   // 3) métodos
        return x + y;
    }
}
```

---

# Las tres partes

| Parte | Para qué |
|---|---|
| **Atributos** | Características de cada objeto |
| **Constructor** | Mismo nombre que la clase, **sin** tipo de retorno. Inicializa los atributos |
| **Métodos** | Acciones. Reciben **parámetros** y pueden devolver un valor con `return` |

Cada `{ }` abre un **bloque**.

---

# Comentarios

```java
// una línea
/* varias
   líneas */
/** Javadoc: documentación
    (Ctrl+J en BlueJ) */
```

Las palabras de color (`public`, `class`, `int`…) son **reservadas**: no las uses como nombres.

---

# Probar en BlueJ

1. **Compile**
2. Clic derecho en la clase → `new Ejemplo()` → objeto
3. Doble clic en el objeto → **Inspector** (su estado)
4. Clic derecho en el objeto → ejecutar un **método**

> [!warning] Devolver ≠ imprimir
> `return` **entrega** un valor; `println` solo lo **muestra**.

---

# Tipos enteros

| Tipo | Bits | Rango |
|---|---|---|
| `byte` | 8 | −128 … 127 |
| `short` | 16 | −32 768 … 32 767 |
| **`int`** | 32 | ± 2 147 483 647 |
| `long` | 64 | enorme → sufijo **`L`** |

**`int`** es el entero por defecto.

---

# Decimales, lógicos y caracteres

| Tipo | Guarda | Ejemplo |
|---|---|---|
| `float` | decimal 32 bits | `4.5F` |
| **`double`** | decimal 64 bits | `1234.56` |
| `boolean` | verdadero / falso | `true` |
| `char` | **un** carácter | `'D'` |

**`double`** es el decimal por defecto.

---

# String

```java
String nombre = "Merlín";      // comillas DOBLES
char inicial = 'U';            // comillas SIMPLES
```

`String` **no** es primitivo: es una **clase** que trae Java (por eso empieza con mayúscula).

---

# Errores típicos

```java
byte b = 288;            // no cabe en byte
long x = 9000000000;     // falta la L
float f = 4.5;           // falta la F
char c = D;              // faltan comillas simples
```

Lee **siempre** el mensaje del compilador: te dice qué pasa y en qué línea.

---

# char es un número

| Carácter | Código |
|---|---|
| `'0'`…`'9'` | 48…57 |
| `'A'`…`'Z'` | 65…90 |
| `'a'`…`'z'` | 97…122 |

```java
char letra = 68;              // 'D'
System.out.println('h' - 'a'); // 7
```

---

# Variables

Un **espacio en memoria con nombre** que guarda un valor de un tipo.

```java
int edad;           // declaración
edad = 20;          // asignación
int nota = 75;      // declaración + inicialización
int dia = 24, mes = 3;
```

`=` **asigna**: la derecha se guarda en la izquierda.

---

# Nombres

| Regla (o no compila) | Convención |
|---|---|
| Letras, dígitos, `_` y `$` | Variables: `notaFinal` |
| No empieza con dígito | Clases: `CuentaBancaria` |
| No es palabra reservada | Constantes: `NOTA_MINIMA` |
| `nota` ≠ `Nota` | Nombres que digan algo |

---

# Alcance (scope)

Una variable vive **solo en el bloque donde nació**.

| Tipo | Dónde | Vive |
|---|---|---|
| **Atributo** | en la clase | lo que vive el objeto |
| **Parámetro** | `( )` del método | la llamada |
| **Local** | dentro del método | hasta cerrar su `}` |

---

# Constantes

```java
final double GRAVEDAD = 9.8;
GRAVEDAD = 10;   // ERROR: es final
```

`final` = el valor **no puede cambiar**. Nombre en **MAYÚSCULAS**.

---

# Resumen

- Entrada → proceso → salida, en **binario**
- Algoritmo + **prueba de escritorio**
- Clase = **atributos + constructor + métodos**
- `int` y `double` por defecto · `L` · `F` · `'c'` · `"texto"`
- Variable = espacio con nombre · vive en su **bloque** · `final`

---

# Tu turno

✍️ [[Clase 01 - Práctica]]

➡️ Próxima clase: **operadores, métodos y decisiones**
