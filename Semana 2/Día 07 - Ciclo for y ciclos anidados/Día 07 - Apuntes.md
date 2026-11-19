---
tipo: apuntes
dia: 7
semana: 2
tema: Ciclo for y ciclos anidados
tags: [java, intro-programacion, dia-07, apuntes]
---

# Día 7 · Ciclo `for` y ciclos anidados

> [!info] Datos de la clase
> **Semana 2 · Martes** · **IDE:** BlueJ · **Requisito:** [[Día 06 - Apuntes|Día 6]]
> **Material del día:** [[Día 07 - Diapositivas|Diapositivas]] · [[Día 07 - Práctica|Práctica]] · [[README|Ruta de aprendizaje]]

> [!abstract] Al terminar este día podrás…
> - Repetir un número conocido de veces con **`for`**.
> - Elegir entre `for`, `while` y `do-while`.
> - Controlar un ciclo con **`break`** y **`continue`**.
> - Escribir **ciclos anidados** y hacer su prueba de escritorio.
> - Dibujar **figuras** con asteriscos y generar **series** numéricas.

---

### 1. El ciclo `for`

Cuando **sabes cuántas veces** vas a repetir, `for` junta las tres partes del ciclo en una sola línea:

```java
for (inicialización; condición; actualización) {
    // cuerpo
}
```

```java
for (int i = 1; i <= 5; i++) {
    System.out.print(i + " ");     // 1 2 3 4 5
}
```

| Parte | En el ejemplo | Cuándo se ejecuta |
|---|---|---|
| Inicialización | `int i = 1` | **Una sola vez**, al empezar |
| Condición | `i <= 5` | **Antes** de cada vuelta |
| Actualización | `i++` | **Después** de cada vuelta |

**Es lo mismo que este `while`:**

```java
int i = 1;
while (i <= 5) {
    System.out.print(i + " ");
    i++;
}
```

> [!important] La variable del `for` vive solo dentro del `for`
> `i` se declaró en la inicialización, así que su **alcance** es el ciclo ([[Día 02 - Apuntes#6. Variables|Día 2]]). Después de la llave de cierre, `i` ya no existe.

### 2. Formas comunes del `for`

| Para… | Ciclo |
|---|---|
| Contar de 1 a `n` | `for (int i = 1; i <= n; i++)` |
| Contar de 0 a `n - 1` | `for (int i = 0; i < n; i++)` |
| Contar hacia atrás | `for (int i = n; i >= 1; i--)` |
| De 2 en 2 | `for (int i = 0; i <= n; i += 2)` |
| Múltiplos de 7 entre 100 y 200 | `for (int i = 105; i <= 200; i += 7)` |

> [!example] Tabla de multiplicar
> ```java
> public String tabla(int n) {
>     String r = "";
>     for (int i = 1; i <= 10; i++) {
>         r += n + " x " + i + " = " + (n * i) + "\n";
>     }
>     return r;
> }
> ```

> [!example] Factorial con `for`
> ```java
> public long factorial(int n) {
>     long f = 1;
>     for (int i = 2; i <= n; i++) {
>         f *= i;
>     }
>     return f;
> }
> ```

### 3. Series numéricas

> [!example] Fibonacci: los `n` primeros términos
> ```java
> public String fibonacci(int n) {
>     String r = "";
>     int a = 0, b = 1;
>     for (int i = 1; i <= n; i++) {
>         r += a + " ";
>         int sig = a + b;
>         a = b;
>         b = sig;
>     }
>     return r;      // n = 9 → "0 1 1 2 3 5 8 13 21 "
> }
> ```

> [!example] Serie con signo alterno: $1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots$
> ```java
> public double serieAlterna(int n) {
>     double suma = 0;
>     int signo = 1;
>     for (int i = 1; i <= n; i++) {
>         suma += signo * (1.0 / i);
>         signo = -signo;
>     }
>     return suma;
> }
> ```
> Fíjate en el `1.0`: con `1 / i` sería división **entera** y casi todos los términos darían 0.

### 4. ¿`for`, `while` o `do-while`?

| Situación | Ciclo recomendado |
|---|---|
| Sé **cuántas veces** se repite (de 1 a `n`, 10 veces…) | **`for`** |
| Repito **mientras** se cumpla algo (dígitos, centinela, Euclides) | **`while`** |
| Debo ejecutar **al menos una vez** (validar, menú) | **`do-while`** |

Los tres son equivalentes: cualquier ciclo se puede escribir con cualquiera. Elige el que haga el código **más claro**.

### 5. `break` y `continue`

| Instrucción | Qué hace |
|---|---|
| `break;` | **Sale** del ciclo inmediatamente |
| `continue;` | **Salta** al final de la vuelta actual y sigue con la siguiente |

```java
// Primer múltiplo de 7 mayor que 100
int encontrado = -1;
for (int i = 101; i <= 200; i++) {
    if (i % 7 == 0) {
        encontrado = i;
        break;           // ya lo encontré: no sigo buscando
    }
}

// Sumar del 1 al 20, sin los múltiplos de 3
int suma = 0;
for (int i = 1; i <= 20; i++) {
    if (i % 3 == 0) {
        continue;        // salta este número
    }
    suma += i;
}
```

> [!tip] Úsalos con moderación
> Muchas veces una **bandera** en la condición deja el ciclo más claro que un `break`.

### 6. Ciclos anidados

Un ciclo **dentro** de otro. Por cada vuelta del ciclo **externo**, el ciclo **interno** se ejecuta **completo**.

```java
for (int i = 1; i <= 3; i++) {          // externo: filas
    for (int j = 1; j <= 4; j++) {      // interno: columnas
        System.out.print("(" + i + "," + j + ") ");
    }
    System.out.println();               // salto de línea al terminar cada fila
}
```

```text
(1,1) (1,2) (1,3) (1,4)
(2,1) (2,2) (2,3) (2,4)
(3,1) (3,2) (3,3) (3,4)
```

> [!important] ¿Cuántas veces se ejecuta el cuerpo interno?
> Externo × interno = 3 × 4 = **12** veces.

> [!example] Todas las tablas de multiplicar del 1 al 9
> ```java
> for (int n = 1; n <= 9; n++) {
>     for (int i = 1; i <= 9; i++) {
>         System.out.print(n * i + "\t");
>     }
>     System.out.println();
> }
> ```

### 7. Figuras con asteriscos

Para dibujar figuras, piensa siempre en **filas** (ciclo externo) y en **qué se imprime en cada fila** (ciclos internos).

> [!example] Rectángulo de `alto × ancho`
> ```java
> for (int f = 1; f <= alto; f++) {
>     for (int c = 1; c <= ancho; c++) {
>         System.out.print("*");
>     }
>     System.out.println();
> }
> ```

> [!example] Triángulo rectángulo de altura `n`
> En la fila `f` hay **`f`** asteriscos.
> ```java
> for (int f = 1; f <= n; f++) {
>     for (int c = 1; c <= f; c++) {
>         System.out.print("*");
>     }
>     System.out.println();
> }
> ```
> ```text
> *
> **
> ***
> ****
> ```

> [!example] Pirámide de altura `n`
> En la fila `f` hay **`n - f` espacios** y **`2f - 1` asteriscos**.
> ```java
> for (int f = 1; f <= n; f++) {
>     for (int e = 1; e <= n - f; e++) {
>         System.out.print(" ");
>     }
>     for (int a = 1; a <= 2 * f - 1; a++) {
>         System.out.print("*");
>     }
>     System.out.println();
> }
> ```
> ```text
>    *
>   ***
>  *****
> *******
> ```

> [!tip] El método de la tabla
> Antes de programar una figura, haz una tabla con la **fila**, la cantidad de **espacios** y la cantidad de **símbolos**, y busca la fórmula que relaciona cada columna con el número de fila.
>
> | Fila `f` | Espacios | Asteriscos |
> |---|---|---|
> | 1 | 3 | 1 |
> | 2 | 2 | 3 |
> | 3 | 1 | 5 |
> | 4 | 0 | 7 |
> | fórmula | `n - f` | `2f - 1` |

### 8. Patrones numéricos

La misma técnica sirve para imprimir números en lugar de asteriscos:

```java
for (int f = 1; f <= n; f++) {
    for (int c = 1; c <= f; c++) {
        System.out.print(c);
    }
    System.out.println();
}
```

```text
1
12
123
1234
```

### 9. Prueba de escritorio con ciclos anidados

Una fila por **cada vuelta del ciclo interno**:

```java
int cont = 0;
for (int i = 1; i <= 2; i++) {
    for (int j = i; j <= 3; j++) {
        cont++;
    }
}
```

| `i` | `j` | `cont` |
|---|---|---|
| 1 | 1 | 1 |
| 1 | 2 | 2 |
| 1 | 3 | 3 |
| 2 | 2 | 4 |
| 2 | 3 | 5 |

Resultado: `cont = 5`. El ciclo interno **empieza en `i`**, así que cada vez da menos vueltas.

---

## Resumen

> [!summary] Lo esencial del Día 7
> - `for (inicio; condición; actualización)`: ideal cuando sabes **cuántas veces** repetir.
> - La variable declarada en el `for` solo existe dentro del ciclo.
> - `for` para contar, `while` para "mientras", `do-while` para "al menos una vez".
> - `break` sale del ciclo; `continue` salta a la siguiente vuelta.
> - En ciclos anidados, el interno se ejecuta **completo** por cada vuelta del externo.
> - Figuras: filas en el ciclo externo; espacios y símbolos en los internos, con una fórmula según la fila.

## Siguiente paso

- ✍️ Practica: [[Día 07 - Práctica]]
- 📖 Glosario: [[Glosario]]
- ⬅️ Ayer: [[Día 06 - Apuntes|Día 6 · Ciclos while y do-while]]
- ➡️ Mañana: [[Día 08 - Apuntes|Día 8 · Cadenas]]
