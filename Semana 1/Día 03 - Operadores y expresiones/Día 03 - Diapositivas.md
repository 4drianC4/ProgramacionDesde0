---
tipo: diapositivas
dia: 3
semana: 1
tags: [java, intro-programacion, dia-03, diapositivas]
theme: white
transition: slide
---

# Día 3

## Operadores y expresiones

**Programación desde 0** · Semana 1 · Miércoles

---

# Hoy vamos a…

1. Escribir y **evaluar expresiones**
2. Evitar la trampa de la **división entera**
3. Usar **relacionales** y **lógicos**
4. Respetar la **precedencia**
5. **Convertir tipos** y usar `Math`

Apuntes completos: [[Día 03 - Apuntes]]

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

| Op        | Pregunta              | Ejemplo          |
| --------- | --------------------- | ---------------- |
| `a == b`  | ¿iguales?             | `5 == 5` → true  |
| `a != b`  | ¿distintos?           | `23 != 7` → true |
| `a > b` `a < b`   | ¿mayor? ¿menor?       | `5 < 3` → false  |
| `a >= b` `a <= b` | ¿mayor/menor o igual? | `5 >= 5` → true  |

---

# Cuidado

> [!warning] `x = 5` no es `x == 5`
> `x = 5` **asigna** · `x == 5` **pregunta**

> [!danger] Los String se comparan con `.equals()`
> `nombre.equals("Ana")` ✔ · `nombre == "Ana"` ✘

---

# Operadores lógicos

| Op     | Es true si…              | En español                        |
| ------ | ------------------------ | --------------------------------- |
| `&&`   | **todas** son true       | "es lunes **y** son las 8"        |
| `\|\|` | **al menos una** es true | "abre la cancha **o** el coliseo" |
| `!`    | invierte                 | "**no** llueve"                   |

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
6. `a == b` `a != b`
7. `&&` → 8. `||` → 9. `?:` → 10. `x = y`

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

# Resumen

- `/` entre enteros corta · `%` da el residuo
- `x++` entrega el viejo · `++x` el nuevo
- `&&` todas · `||` alguna · `!` invierte
- String → `.equals()`
- *Casting* `(int)` corta · `Math` tiene lo demás

---

# Tu turno

✍️ [[Día 03 - Práctica]]

➡️ Mañana: **métodos y entrada de datos**
