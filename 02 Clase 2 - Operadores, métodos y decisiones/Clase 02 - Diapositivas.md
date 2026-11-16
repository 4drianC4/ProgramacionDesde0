---
tipo: diapositivas
clase: 2
semanas: [3, 4]
tags: [java, intro-programacion, clase-02, diapositivas]
theme: white
transition: slide
---

# Clase 2

## Operadores, métodos y decisiones

**Programación desde 0** · Apoyo para Introducción a la Programación (INF-135) · UMSS

---

# Hoy vamos a…

1. Escribir y **evaluar expresiones** con operadores
2. **Convertir tipos** y usar `Math`
3. Escribir **métodos** con parámetros y `return`
4. Leer datos con **`Scanner`**
5. Tomar **decisiones** con `if` / `else`

Apuntes completos: [[Clase 02 - Apuntes]]

---

# Semana 3

Expresiones y operadores

---

# ¿Qué es una expresión?

Valores + variables + operadores que **se evalúan** y producen **un** valor.

```java
int total = precio * cantidad + envio;  // → int
boolean puedeVotar = edad >= 18;         // → boolean
```

---

# Operadores aritméticos

| Op | Ejemplo | Resultado |
|---|---|---|
| `+` | `7 + 2` | `9` |
| `-` | `7 - 2` | `5` |
| `*` | `7 * 2` | `14` |
| `/` | `7 / 2` | **`3`** ⚠️ |
| `%` | `7 % 2` | `1` |

---

# La trampa de la división

```java
int    a = 10 / 3;          // 3
double b = 10 / 3;          // 3.0  ← ¡entera!
double c = 10.0 / 3;        // 3.333…
double d = (double) 10 / 3; // 3.333…
```

> [!important] Regla de oro
> El tipo del resultado lo deciden los **operandos**, no la variable.

---

# Módulo `%`: el residuo

| Para… | Expresión |
|---|---|
| ¿Es par? | `n % 2 == 0` |
| ¿`d` divide a `n`? | `n % d == 0` |
| Último dígito | `n % 10` |
| Quitar último dígito | `n / 10` |
| Dar la vuelta (reloj) | `(h + k) % 24` |

---

# Descomponer un número

```java
int n = 427;
int unidades = n % 10;         // 7
int decenas  = (n / 10) % 10;  // 2
int centenas = n / 100;        // 4
```

Esto aparece en **muchos** ejercicios de examen.

---

# Asignación compuesta

| Corto | Largo |
|---|---|
| `x += 5;` | `x = x + 5;` |
| `x -= 5;` | `x = x - 5;` |
| `x *= 5;` | `x = x * 5;` |
| `x %= 5;` | `x = x % 5;` |

Contador: `c += 1;` · Acumulador: `s += x;`

---

# `x++` vs `++x`

```java
int suma = 2;
int v1 = suma++;  // v1 = 2, suma = 3
int v2 = ++suma;  // suma = 4, v2 = 4
```

- `x++` → "úsame y **después** cámbiame"
- `++x` → "cámbiame y **después** úsame"

---

# Operadores relacionales

Hacen una **pregunta** → `true` o `false`

| Op | Pregunta | Ejemplo |
|---|---|---|
| `==` | ¿iguales? | `5 == 5` → true |
| `!=` | ¿distintos? | `23 != 7` → true |
| `>` `<` | ¿mayor? ¿menor? | `5 < 3` → false |
| `>=` `<=` | ¿mayor/menor o igual? | `5 >= 5` → true |

---

# Cuidado

> [!warning] `=` no es `==`
> `=` **asigna** · `==` **pregunta**

> [!danger] Los String se comparan con `.equals()`
> `nombre.equals("Ana")` ✔ · `nombre == "Ana"` ✘

---

# Operadores lógicos

| Op | Es true si… | En español |
|---|---|---|
| `&&` | **todas** son true | "es lunes **y** son las 8" |
| `\|\|` | **al menos una** es true | "abre la cancha **o** el coliseo" |
| `!` | invierte | "**no** llueve" |

```java
boolean enRango = nota >= 0 && nota <= 100;
```

---

# Tabla de verdad

| a | b | a && b | a \|\| b | !a |
|---|---|---|---|---|
| T | T | **T** | **T** | F |
| T | F | F | **T** | F |
| F | T | F | **T** | **T** |
| F | F | F | F | **T** |

---

# Precedencia

1. `( )`
2. `++` `--` `!` · casting
3. `*` `/` `%`
4. `+` `-`
5. `<` `>` `<=` `>=`
6. `==` `!=`
7. `&&` → 8. `||` → 9. `?:` → 10. `=`

**Ante la duda, paréntesis.**

---

# Evaluemos

`3 + 4 * 2 > 10 && 7 % 2 == 1`

1. `4 * 2` → 8 · `7 % 2` → 1
2. `3 + 8` → 11
3. `11 > 10` → true · `1 == 1` → true
4. `true && true` → **true**

---

# Casting

```java
double real = 7;                  // 7.0 (automático)
int corto = (int) 9.99;           // 9 (corta, NO redondea)
long red = Math.round(9.99);      // 10
char sig = (char) ('a' + 1);      // 'b'
```

Pequeño → grande: automático · Grande → pequeño: **`(tipo)`**

---

# La clase Math

| Método | Ejemplo |
|---|---|
| `Math.pow(b, e)` | `pow(2, 10)` → 1024.0 |
| `Math.sqrt(x)` | `sqrt(49)` → 7.0 |
| `Math.abs(x)` | `abs(-5)` → 5 |
| `Math.max` / `min` | `max(3, 8)` → 8 |
| `Math.random()` | [0, 1) |

---

# Aleatorio en un rango

Entero en **[inf, sup)**:

```java
int n = (int) (Math.random() * (sup - inf)) + inf;
```

Ejemplo: número objetivo en [10, 60):

```java
int objetivo = (int) (Math.random() * 50) + 10;
```

---

# `+` con texto

```java
"Total: " + 3 + 4      // "Total: 34"
"Total: " + (3 + 4)    // "Total: 7"
```

Si hay un `String`, el `+` **une textos** (de izquierda a derecha).

---

# Semana 4

Métodos, entrada de datos y decisiones

---

# Estructura de un método

```java
public int sumar(int a, int b) {
    int suma = a + b;
    return suma;
}
```

**acceso** · **tipo de retorno** · **nombre** · **(parámetros)** · **{ cuerpo }** · **return**

---

# Las partes

| Parte | Ejemplos |
|---|---|
| Acceso | `public` · `private` |
| Retorno | `int` `double` `boolean` `String` · **`void`** |
| Nombre | verbo en camelCase: `calcularPromedio` |
| Parámetros | datos que llegan de afuera |
| `return` | entrega el resultado |

---

# Tres formas comunes

```java
public double promedio(double a, double b) {
    return (a + b) / 2;
}
public boolean esPar(int n) {
    return n % 2 == 0;
}
public void reiniciar() {
    contador = 0;
}
```

---

# Métodos que usan métodos

```java
public double promedioTres(double a, double b, double c) {
    return (a + b + c) / 3;
}
public String estado(double a, double b, double c) {
    double p = promedioTres(a, b, c);
    return p >= 51 ? "APROBADO" : "REPROBADO";
}
```

Divide un problema grande en partes pequeñas.

---

# static

- **Sin** `static` → del **objeto** → primero `new`
- **Con** `static` → de la **clase** → `Math.sqrt(9)`

> [!warning] Error frecuente
> *non-static method cannot be referenced from a static context* → crea un objeto o usa `static`.

---

# main + Scanner

```java
import java.util.Scanner;

public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int n1 = sc.nextInt();
    int n2 = sc.nextInt();
    Calculadora calc = new Calculadora();
    System.out.println(calc.sumar(n1, n2));
}
```

---

# El patrón del curso

**Usuario escribe → Scanner lee → variables → método de lógica → return → println muestra**

> [!important] Devolver vs. mostrar
> La **lógica devuelve**. Solo `main` **imprime**.

---

# Leer con Scanner

| Método | Lee |
|---|---|
| `nextInt()` | `int` |
| `nextDouble()` | `double` |
| `next()` | una palabra |
| `nextLine()` | una línea |
| `next().charAt(0)` | un `char` |

---

# Dos trampas de Scanner

1. `nextDouble()` y la **coma decimal** →
   `sc.useLocale(java.util.Locale.US);`
2. `nextLine()` después de `nextInt()` lee **vacío** →
   agrega un `sc.nextLine();` extra

---

# if: tomar decisiones

```java
if (precio > 100) {
    res = precio * 0.9;
}
```

Se ejecuta **solo si** la condición es `true`.

La condición es **una pregunta**: una expresión `boolean`.

---

# if - else

```java
if (nota >= 51) {
    res = "APROBADO";
} else {
    res = "REPROBADO";
}
```

Uno de los dos **siempre** se ejecuta, **nunca** ambos.
El `else` no lleva condición.

---

# else if

```java
if (nota < 0 || nota > 100) {
    res = "NOTA INVÁLIDA";
} else if (nota >= 51) {
    res = "APROBADO";
} else if (nota >= 50) {
    res = "CASO ESPECIAL";
} else {
    res = "REPROBADO";
}
```

Se ejecuta la **primera** condición verdadera.

---

# Anidados y ternario

```java
if (monto > 0) {
    if (monto <= saldo) { res = "Retiro exitoso"; }
    else { res = "Saldo insuficiente"; }
}
```

```java
int mayor = a > b ? a : b;
```

---

# Tres errores clásicos

```java
if (nota >= 51);          // el ; termina el if
if (nota >= 51)
    res = "APROBADO";
    contador++;           // NO es parte del if
if (nombre == "Ana")      // usa .equals()
```

**Siempre usa llaves.**

---

# Probar un if

**Un dato por cada camino + los límites**

| nota | Resultado |
|---|---|
| 75 | APROBADO |
| 51 | APROBADO (límite) |
| 50.5 | CASO ESPECIAL |
| 30 | REPROBADO |
| 120 | NOTA INVÁLIDA |

---

# Resumen

- `/` entre enteros corta · `%` da el residuo
- `x++` entrega el viejo · `++x` el nuevo
- `&&` todas · `||` alguna · `!` invierte · String → `.equals()`
- Método = acceso + retorno + nombre + parámetros + `return`
- `main` lee con **Scanner**, llama y muestra
- `if` / `else if` / `else` con llaves

---

# Tu turno

✍️ [[Clase 02 - Práctica]]

➡️ Siguen las semanas de **resolución de ejercicios**
