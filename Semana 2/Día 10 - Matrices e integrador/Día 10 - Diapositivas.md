---
tipo: diapositivas
dia: 10
semana: 2
tags: [java, intro-programacion, dia-10, diapositivas]
theme: white
transition: slide
---

# Día 10

## Matrices e integrador

**Programación desde 0** · Semana 2 · Viernes

---

# Hoy vamos a…

1. **Crear y recorrer** matrices
2. Sumar por **fila**, **columna** y **diagonal**
3. Usar una matriz como **atributo**
4. Diseñar **clases que colaboran**
5. Enfrentar un **problema integrador**

Apuntes completos: [[Día 10 - Apuntes]]

---

# ¿Qué es una matriz?

Datos en **filas** y **columnas**: `m[fila][columna]`

| | c0 | c1 | c2 | c3 |
|---|---|---|---|---|
| **f0** | 5 | 2 | 8 | 1 |
| **f1** | 3 | 7 | **4** | 6 |
| **f2** | 9 | 0 | 2 | 5 |

`m[1][2]` → **4**

---

# Crear

```java
int[][] m = new int[3][4];
int[][] t = {
    {5, 2, 8, 1},
    {3, 7, 4, 6},
    {9, 0, 2, 5}
};
```

- `t.length` → **3** filas
- `t[0].length` → **4** columnas

---

# Recorrer

```java
for (int f = 0; f < m.length; f++) {
    for (int c = 0; c < m[f].length; c++) {
        System.out.print(m[f][c] + "\t");
    }
    System.out.println();
}
```

Filas **afuera**, columnas **adentro**.

---

# Fila fija, columna fija

```java
// suma de la fila f: cambia c
for (int c = 0; c < m[f].length; c++)
    s += m[f][c];

// suma de la columna c: cambia f
for (int f = 0; f < m.length; f++)
    s += m[f][c];
```

---

# Diagonales

| Región | Condición |
|---|---|
| Principal | `f == c` |
| Secundaria | `f + c == n - 1` |
| Sobre la principal | `c > f` |
| Bajo la principal | `c < f` |

```java
for (int i = 0; i < n; i++)
    s += m[i][i];        // un solo ciclo
```

---

# Transpuesta

```java
int[][] t = new int[m[0].length][m.length];
for (int f = 0; f < m.length; f++)
    for (int c = 0; c < m[f].length; c++)
        t[c][f] = m[f][c];
```

Rotar 90° = transpuesta + invertir cada fila

---

# Espiral

Cuatro límites que se achican:

- `arriba` → recorre la fila de arriba
- `der` → baja por la columna derecha
- `abajo` → vuelve por la fila de abajo
- `izq` → sube por la columna izquierda

`1 2 3 4 8 12 11 10 9 5 6 7`

---

# Matriz como atributo

```java
private int[][] cantidades;   // [agencia][producto]
private double[] precios;     // [producto]

public double recaudacion(int a) {
    double t = 0;
    for (int p = 0; p < precios.length; p++)
        t += cantidades[a][p] * precios[p];
    return t;
}
```

---

# Clases que colaboran

```java
public class Colegio {
    private Curso[] cursos = new Curso[14];
    private int cantidad = 0;
    …
}
```

Un **arreglo de objetos** reemplaza a muchos arreglos paralelos.

---

# Usar objetos del arreglo

```java
Curso mayor = cursos[0];
for (int i = 1; i < cantidad; i++) {
    if (cursos[i].getEstudiantes() > mayor.getEstudiantes()) {
        mayor = cursos[i];
    }
}
```

---

# Problema integrador

1. **Sustantivos** → clases y atributos
2. **Verbos** → métodos
3. ¿Valor, **arreglo**, **matriz** u **objeto**?
4. **Un método a la vez**, probado en BlueJ
5. **Prueba de escritorio** de los ciclos
6. El `main` al final

---

# Resumen

- `m[f][c]` · `m.length` filas · `m[0].length` columnas
- Dos `for`: filas afuera, columnas adentro
- Principal `f == c` · secundaria `f + c == n - 1`
- Arreglo de **objetos** + contador
- Sustantivos → clases · verbos → métodos

---

# ¡Terminamos la teoría! 🎉

✍️ [[Día 10 - Práctica]]

➡️ Siguen las semanas de **resolución de ejercicios**
