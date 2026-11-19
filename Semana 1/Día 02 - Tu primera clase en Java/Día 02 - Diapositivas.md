---
tipo: diapositivas
dia: 2
semana: 1
tags: [java, intro-programacion, dia-02, diapositivas]
theme: white
transition: slide
---

# Día 2

## Tu primera clase en Java

**Programación desde 0** · Semana 1 · Martes

---

# Hoy vamos a…

1. Instalar y usar **BlueJ**
2. Conocer la estructura de una **clase**
3. Usar **tipos de datos**
4. Declarar **variables** y **constantes**

Apuntes completos: [[Día 02 - Apuntes]]

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

`edad = 20` **asigna**: la derecha se guarda en la izquierda.

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

- Clase = **atributos + constructor + métodos**
- BlueJ: compilar → objeto → inspector → métodos
- `int` y `double` por defecto · `L` · `F` · `'c'` · `"texto"`
- Variable = espacio con nombre · vive en su **bloque** · `final`

---

# Tu turno

✍️ [[Día 02 - Práctica]]

➡️ Mañana: **operadores y expresiones**
