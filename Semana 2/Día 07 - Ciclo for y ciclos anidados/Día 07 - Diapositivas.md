---
tipo: diapositivas
dia: 7
semana: 2
tags: [java, intro-programacion, dia-07, diapositivas]
theme: white
transition: slide
---

# Día 7

## Ciclo for y ciclos anidados

**Programación desde 0** · Semana 2 · Martes

---

# Hoy vamos a…

1. Repetir con **`for`**
2. Elegir entre **`for`, `while` y `do-while`**
3. Usar **`break`** y **`continue`**
4. **Anidar** ciclos
5. Dibujar **figuras** y generar **series**

Apuntes completos: [[Día 07 - Apuntes]]

---

# for

```java
for (int i = 1; i <= 5; i++) {
    System.out.print(i + " ");
}
// 1 2 3 4 5
```

Las **tres partes** del ciclo en una sola línea.

---

# Las partes del for

| Parte | Ejemplo | Cuándo |
|---|---|---|
| Inicialización | `int i = 1` | una vez |
| Condición | `i <= 5` | antes de cada vuelta |
| Actualización | `i++` | después de cada vuelta |

`i` solo existe **dentro** del `for`.

---

# for = while

```java
for (int i = 1; i <= 5; i++) {
    System.out.print(i);
}
```

```java
int i = 1;
while (i <= 5) {
    System.out.print(i);
    i++;
}
```

---

# Formas comunes

| Para… | Ciclo |
|---|---|
| 1 a n | `for (int i = 1; i <= n; i++)` |
| 0 a n-1 | `for (int i = 0; i < n; i++)` |
| hacia atrás | `for (int i = n; i >= 1; i--)` |
| de 2 en 2 | `for (int i = 0; i <= n; i += 2)` |

---

# Factorial

```java
long f = 1;
for (int i = 2; i <= n; i++) {
    f *= i;
}
```

---

# Fibonacci

```java
int a = 0, b = 1;
for (int i = 1; i <= n; i++) {
    System.out.print(a + " ");
    int sig = a + b;
    a = b;
    b = sig;
}
```

`0 1 1 2 3 5 8 13 21`

---

# ¿Cuál ciclo uso?

| Situación | Ciclo |
|---|---|
| Sé **cuántas veces** | `for` |
| **Mientras** algo pase | `while` |
| **Al menos una vez** | `do-while` |

Todos son equivalentes: elige el **más claro**.

---

# break y continue

```java
for (int i = 101; i <= 200; i++) {
    if (i % 7 == 0) {
        encontrado = i;
        break;        // sale del ciclo
    }
}
```

`continue;` salta a la **siguiente vuelta**.

---

# Ciclos anidados

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 4; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

El interno se ejecuta **completo** por cada vuelta del externo: 3 × 4 = **12**.

---

# Triángulo

```java
for (int f = 1; f <= n; f++) {
    for (int c = 1; c <= f; c++) {
        System.out.print("*");
    }
    System.out.println();
}
```

En la fila `f` hay **`f`** asteriscos.

---

# Pirámide: la tabla

| Fila | Espacios | Asteriscos |
|---|---|---|
| 1 | 3 | 1 |
| 2 | 2 | 3 |
| 3 | 1 | 5 |
| 4 | 0 | 7 |
| **fórmula** | **n − f** | **2f − 1** |

---

# Pirámide: el código

```java
for (int f = 1; f <= n; f++) {
    for (int e = 1; e <= n - f; e++)
        System.out.print(" ");
    for (int a = 1; a <= 2 * f - 1; a++)
        System.out.print("*");
    System.out.println();
}
```

---

# Patrones numéricos

```java
for (int f = 1; f <= n; f++) {
    for (int c = 1; c <= f; c++) {
        System.out.print(c);
    }
    System.out.println();
}
```

`1` · `12` · `123` · `1234`

---

# Prueba de escritorio anidada

`for i 1..2 { for j = i..3 { cont++ } }`

| i | j | cont |
|---|---|---|
| 1 | 1 | 1 |
| 1 | 2 | 2 |
| 1 | 3 | 3 |
| 2 | 2 | 4 |
| 2 | 3 | 5 |

---

# Resumen

- `for`: cuando sabes **cuántas veces**
- `break` sale · `continue` salta
- Anidados: interno **completo** por cada externo
- Figuras: tabla **fila / espacios / símbolos**

---

# Tu turno

✍️ [[Día 07 - Práctica]]

➡️ Mañana: **cadenas `String` y `char`**
