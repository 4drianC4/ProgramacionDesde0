---
tipo: apuntes
dia: 3
semana: 1
tema: Operadores y expresiones
tags: [java, intro-programacion, dia-03, apuntes]
---

# Día 3 · Operadores y expresiones

> [!info] Datos de la clase
> **Semana 1 · Miércoles** · **IDE:** BlueJ · **Requisito:** [[Día 02 - Apuntes|Día 2]]
> **Material del día:** [[Día 03 - Diapositivas|Diapositivas]] · [[Día 03 - Práctica|Práctica]] · [[README|Ruta de aprendizaje]]

> [!abstract] Al terminar este día podrás…
> - Escribir y **evaluar expresiones** con operadores aritméticos, relacionales y lógicos.
> - Evitar las trampas típicas: **división entera**, `++` antes y después, comparar `String` con `a == b`.
> - Usar el operador **módulo** para pares, divisores y dígitos.
> - Respetar la **precedencia** de operadores.
> - **Convertir tipos** (*casting*) y usar la clase `Math`.

---

### 1. ¿Qué es una expresión?

Una **expresión** es una combinación de valores, variables y operadores que **se evalúa** y produce **un** valor.

```java
int total = precio * cantidad + envio;   // expresión aritmética → int
boolean puedeVotar = edad >= 18;          // expresión relacional → boolean
```

### 2. Operadores aritméticos

| Operador | Operación        | Ejemplo | Resultado |
| -------- | ---------------- | ------- | --------- |
| `+`      | suma             | `7 + 2` | `9`       |
| `-`      | resta            | `7 - 2` | `5`       |
| `*`      | multiplicación   | `7 * 2` | `14`      |
| `/`      | división         | `7 / 2` | `3` ⚠️    |
| `%`      | módulo (residuo) | `7 % 2` | `1`       |

#### ⚠️ La trampa de la división entera

Si **los dos operandos son enteros**, el resultado es **entero** (se descarta la parte decimal), **sin importar** dónde lo guardes.

```java
int    a = 10 / 3;     // 3
double b = 10 / 3;     // 3.0  ← ¡sigue siendo división entera!
double c = 10.0 / 3;   // 3.3333333333333335 ✔
double d = (double) 10 / 3; // 3.3333333333333335 ✔ (casting)
```

> [!important] Regla de oro
> El tipo del resultado lo deciden los **operandos**, no la variable donde lo guardas. Para obtener decimales, al menos **uno** de los operandos tiene que ser `double`.

#### El operador módulo `%`

`n % m` devuelve **lo que sobra** de dividir `n` entre `m`.

```text
   10 | 3
   -9   3   ← cociente:  10 / 3 = 3
   --
    1       ← residuo:   10 % 3 = 1
```

Es uno de los operadores más útiles en los ejercicios de la materia:

| Para… | Expresión | Ejemplo |
|---|---|---|
| Saber si `n` es **par** | `n % 2 == 0` | `8 % 2` → `0` |
| Saber si `d` **divide** a `n` | `n % d == 0` | `15 % 5` → `0` |
| Obtener el **último dígito** | `n % 10` | `427 % 10` → `7` |
| **Quitar** el último dígito | `n / 10` | `427 / 10` → `42` |
| "Dar la vuelta" (reloj, días) | `(h + k) % 24` | `(22 + 5) % 24` → `3` |

> [!example] Descomponer un número de 3 cifras
> ```java
> int n = 427;
> int unidades = n % 10;          // 7
> int decenas  = (n / 10) % 10;   // 2
> int centenas = n / 100;         // 4
> ```

### 3. Asignación compuesta

| Forma corta | Equivale a |
|---|---|
| `x += 5;` | `x = x + 5;` |
| `x -= 5;` | `x = x - 5;` |
| `x *= 5;` | `x = x * 5;` |
| `x /= 5;` | `x = x / 5;` |
| `x %= 5;` | `x = x % 5;` |

El **contador** y el **acumulador** del [[Día 01 - Apuntes#6. Elementos básicos de un algoritmo|Día 1]] se escriben así: `c += 1;` y `s += x;`.

### 4. Incremento y decremento: `++` y `--`

`x++` y `++x` suman 1 a `x`. La diferencia está en **qué valor entregan** a la expresión:

| Forma | Nombre | Se lee | Qué pasa |
|---|---|---|---|
| `x++` | post-incremento | "úsame y **después** cámbiame" | entrega el valor **viejo**, luego suma 1 |
| `++x` | pre-incremento | "cámbiame y **después** úsame" | suma 1, luego entrega el valor **nuevo** |

```java
int suma = 2;
int v1 = suma++;   // v1 = 2, suma = 3
int v2 = ++suma;   // suma = 4, v2 = 4
```

> [!tip] Consejo práctico
> Usa `x++` **solo** en su propia línea (`contador++;`). Dentro de expresiones más largas confunde y es fuente de errores.

### 5. Operadores relacionales

Comparan dos valores y **siempre** devuelven un `boolean`. Léelos como **preguntas**.

| Operador | Pregunta | Ejemplo | Resultado |
|---|---|---|---|
| `a == b` | ¿son iguales? | `5 == 5` | `true` |
| `a != b` | ¿son distintos? | `23 != 7` | `true` |
| `a > b` | ¿es mayor? | `5 > 3` | `true` |
| `a < b` | ¿es menor? | `5 < 3` | `false` |
| `a >= b` | ¿es mayor o igual? | `5 >= 5` | `true` |
| `a <= b` | ¿es menor o igual? | `5 <= 3` | `false` |

> [!warning] `x = 5` no es `x == 5`
> `x = 5` **asigna** el valor 5 a `x`. `x == 5` **pregunta** si `x` vale 5.

> [!danger] Comparar `String`: usa `.equals()`
> ```java
> String a = "java";
> boolean b1 = a.equals("java");            // ✔ compara el contenido
> boolean b2 = a.equalsIgnoreCase("JAVA");  // ✔ sin importar mayúsculas
> boolean b3 = a == "java";                 // ✘ compara referencias: a veces falla
> ```
> `String` es una clase (no primitivo); `a == b` compara si son **el mismo objeto**, no si tienen el mismo texto.

### 6. Operadores lógicos

Sirven para **unir preguntas**. Trabajan con valores `boolean`.

| Operador | Nombre | Es `true` cuando… | Lenguaje natural |
|---|---|---|---|
| `&&` | Y (AND) | **todas** las condiciones son `true` | "es lunes **y** son las 8 → trabajo" |
| `\|\|` | O (OR) | **al menos una** es `true` | "la cancha de fútbol **o** la de vóley está abierta → hago deporte" |
| `!` | NO (NOT) | invierte el valor | "**no** llueve" |

**Tabla de verdad**

| `a` | `b` | `a && b` | `a \|\| b` | `!a` |
|---|---|---|---|---|
| `true` | `true` | `true` | `true` | `false` |
| `true` | `false` | `false` | `true` | `false` |
| `false` | `true` | `false` | `true` | `true` |
| `false` | `false` | `false` | `false` | `true` |

```java
boolean enRango   = nota >= 0 && nota <= 100;
boolean esVocal   = c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
boolean esImpar   = !(n % 2 == 0);
```

> [!tip] Evaluación en cortocircuito
> En `a && b`, si `a` es `false`, Java **ni mira** `b` (ya sabe que el resultado es `false`). En `a || b`, si `a` es `true`, tampoco mira `b`. Eso permite escribir con seguridad: `divisor != 0 && n % divisor == 0`.

> [!warning] No confundas `&&` con `&`
> `&`, `|`, `^`, `~`, `<<`, `>>` son operadores **a nivel de bits**. Existen, pero no son parte de esta materia. Si escribes `&` por error, a veces compila y da resultados inesperados.

### 7. Precedencia: ¿qué se evalúa primero?

De **mayor** a **menor** prioridad (los de la misma fila se evalúan de izquierda a derecha):

| Prioridad | Operadores                                           |
| --------- | ---------------------------------------------------- |
| 1         | `( )` paréntesis                                     |
| 2         | `++` `--` `!` `-` (unario) · *casting* `(int)`       |
| 3         | `*` `/` `%`                                          |
| 4         | `+` `-`                                              |
| 5         | `<` `>` `<=` `>=`                                    |
| 6         | `a == b` `a != b`                                    |
| 7         | `&&`                                                 |
| 8         | `\|\|`                                               |
| 9         | `?:` (ternario)                                      |
| 10        | `x = y` `x += y` `x -= y` … (asignación, de derecha a izquierda) |

> [!example] Evaluación paso a paso
> `3 + 4 * 2 > 10 && 7 % 2 == 1`
> 1. `4 * 2` → `8`, y `7 % 2` → `1`
> 2. `3 + 8` → `11`
> 3. `11 > 10` → `true`, y `1 == 1` → `true`
> 4. `true && true` → **`true`**

> [!tip] Ante la duda, paréntesis
> `(a + b) / 2` y `a + b / 2` son cosas distintas. Los paréntesis hacen el código más claro aunque no sean obligatorios.

### 8. Conversión de tipos (*casting*)

- **Implícita (ensanchamiento):** de un tipo "pequeño" a uno "grande", Java lo hace solo.
  `byte → short → int → long → float → double` · `char → int`
- **Explícita (*casting*):** de "grande" a "pequeño" debes pedirlo tú, y **puedes perder información**.

```java
int    entero  = 7;
double real    = entero;          // 7.0  (implícita)
double precio  = 9.99;
int    truncado = (int) precio;   // 9    (explícita: corta, NO redondea)
long   redondo = Math.round(precio); // 10

char   letra = 'a';
int    codigo = letra;            // 97
char   siguiente = (char) (letra + 1); // 'b'
```

### 9. La clase `Math`

Métodos **estáticos** listos para usar (no necesitas crear un objeto):

| Método | Devuelve | Ejemplo |
|---|---|---|
| `Math.pow(b, e)` | $b^e$ (`double`) | `Math.pow(2, 10)` → `1024.0` |
| `Math.sqrt(x)` | $\sqrt{x}$ | `Math.sqrt(49)` → `7.0` |
| `Math.abs(x)` | valor absoluto | `Math.abs(-5)` → `5` |
| `Math.max(a, b)` / `Math.min(a, b)` | mayor / menor | `Math.max(3, 8)` → `8` |
| `Math.round(x)` | redondeo al entero más cercano | `Math.round(2.5)` → `3` |
| `Math.PI` | π | `3.141592653589793` |
| `Math.random()` | `double` aleatorio en $[0, 1)$ | `0.7231…` |

> [!example] Número aleatorio en un rango (sale en exámenes)
> Para un entero en $[\text{inf}, \text{sup})$ (el límite superior **no** se alcanza):
> ```java
> int n = (int) (Math.random() * (sup - inf)) + inf;
> ```
> Ejemplo: número objetivo en $[10, 60)$ → `(int) (Math.random() * 50) + 10`.

### 10. `+` con `String`: concatenación

Si uno de los operandos de `+` es un `String`, el `+` **une textos**.

```java
String msg = "Nota: " + 85;      // "Nota: 85"
System.out.println("Total: " + 3 + 4);   // "Total: 34"  ← se evalúa de izquierda a derecha
System.out.println("Total: " + (3 + 4)); // "Total: 7"   ✔
```


---

## Resumen

> [!summary] Lo esencial del Día 3
> - `/` entre enteros **descarta** decimales. `%` da el **residuo**: sirve para pares, divisores y dígitos.
> - `x++` entrega el valor **viejo**; `++x`, el **nuevo**.
> - Los relacionales y lógicos devuelven `boolean`. `&&`: todas; `||`: al menos una; `!`: invierte.
> - `String` se compara con **`.equals()`**, nunca con `a == b`.
> - *Casting*: `(int) 9.99` → `9` (corta). Aleatorio en $[inf, sup)$: `(int)(Math.random()*(sup-inf))+inf`.
> - Ante la duda sobre la precedencia, usa **paréntesis**.

## Siguiente paso

- ✍️ Practica: [[Día 03 - Práctica]]
- 📖 Glosario: [[Glosario]]
- ⬅️ Ayer: [[Día 02 - Apuntes|Día 2 · Tu primera clase en Java]]
- ➡️ Mañana: [[Día 04 - Apuntes|Día 4 · Métodos y entrada de datos]]
