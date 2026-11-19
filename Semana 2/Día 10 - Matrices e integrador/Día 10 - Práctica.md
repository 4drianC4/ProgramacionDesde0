---
tipo: practica
dia: 10
semana: 2
tema: Matrices, recorridos y clases que colaboran
tags: [java, intro-programacion, dia-10, practica]
---

# Práctica · Día 10

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 10 - Apuntes|apuntes del Día 10]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto (estilo examen).
> - Proyecto de BlueJ: `Dia10`. En BlueJ puedes pasar una matriz como parámetro así: `{{1, 2}, {3, 4}}`.
> - Esta práctica cierra las 2 semanas de teoría: la Parte E integra **todo** el curso.

---

## Parte A · Seguir el código (en papel)

Con esta matriz:

```java
int[][] m = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

- [ ] **A1** ⭐ ¿Qué vale? `m.length` · `m[0].length` · `m[2][1]` · `m[1][2]` · `m[m.length - 1][0]`
- [ ] **A2** ⭐⭐ ¿Qué imprime?
  ```java
  for (int c = 0; c < 3; c++) {
      for (int f = 0; f < 3; f++) {
          System.out.print(m[f][c] + " ");
      }
      System.out.println();
  }
  ```
- [ ] **A3** ⭐⭐ ¿Qué devuelve este método con `m`? ¿Qué región suma?
  ```java
  public int region(int[][] m) {
      int s = 0;
      for (int f = 0; f < m.length; f++) {
          for (int c = f; c < m.length; c++) {
              s += m[f][c];
          }
      }
      return s;
  }
  ```
- [ ] **A4** ⭐⭐ ¿Qué valores recorre `espiral` (de los apuntes) con una matriz de 3 × 4 que tiene los números del 1 al 12 por filas?

> [!question]- Respuestas de la Parte A
> **A1:** `3` · `3` · `8` · `6` · `7`
>
> **A2:** la matriz **por columnas** (la transpuesta): `1 4 7` / `2 5 8` / `3 6 9`.
>
> **A3:** `26`: suma la diagonal principal y lo que está **sobre** ella (1+2+3+5+6+9).
>
> **A4:** `1 2 3 4 8 12 11 10 9 5 6 7`

---

## Parte B · Recorridos básicos

Clase `Matrices`, un método por ejercicio:

- [ ] **B1** ⭐ `void llenar(int[][] m)` con datos leídos y `String mostrar(int[][] m)` en forma de tabla.
- [ ] **B2** ⭐ `int sumaTotal(int[][] m)` y `double promedio(int[][] m)`
- [ ] **B3** ⭐ `int[] sumasPorFila(int[][] m)` y `int[] sumasPorColumna(int[][] m)`
- [ ] **B4** ⭐⭐ `String maximoConPosicion(int[][] m)`
- [ ] **B5** ⭐⭐ `int contar(int[][] m, int x)` y `String posiciones(int[][] m, int x)` → todas las posiciones donde aparece `x`.
- [ ] **B6** ⭐⭐ `int[][] transpuesta(int[][] m)`
- [ ] **B7** ⭐⭐ `int[][] sumar(int[][] a, int[][] b)` → suma de matrices del mismo tamaño.
- [ ] **B8** ⭐⭐⭐ `int[][] multiplicar(int[][] a, int[][] b)` → producto de matrices (columnas de `a` = filas de `b`).

---

## Parte C · Matrices cuadradas

- [ ] **C1** ⭐ `int sumaDiagonalPrincipal(int[][] m)` y `int sumaDiagonalSecundaria(int[][] m)`
- [ ] **C2** ⭐⭐ `boolean esSimetrica(int[][] m)` → <code>m[f][c] &#61;&#61; m[c][f]</code> para todo `f`, `c`.
- [ ] **C3** ⭐⭐ `boolean esIdentidad(int[][] m)` → 1 en la diagonal principal y 0 en el resto.
- [ ] **C4** ⭐⭐ `int sumaBorde(int[][] m)`
- [ ] **C5** ⭐⭐ `String triangularInferior(int[][] m)` → muestra solo la diagonal y lo que está debajo (con espacios en el resto).
- [ ] **C6** ⭐⭐⭐ `boolean esCuadradoMagico(int[][] m)` → todas las filas, columnas y las dos diagonales suman lo mismo.
- [ ] **C7** ⭐⭐⭐ `int[][] rotar90(int[][] m)` → rota una matriz cuadrada 90° a la derecha.
- [ ] **C8** ⭐⭐⭐ `String espiral(int[][] m)` → escríbelo **sin mirar** los apuntes y haz su prueba de escritorio con una matriz de 4 × 4.

---

## Parte D · Matrices como atributo

- [ ] **D1** ⭐⭐ **Comercializadora.** Completa la clase de los apuntes (4 agencias × 5 productos) con:
  1. La cantidad total vendida de cada producto.
  2. La cantidad de productos vendidos por cada agencia.
  3. La cantidad de un producto en una agencia.
  4. La recaudación de cada agencia y la total de la empresa.
  5. Las **dos** agencias con mayor recaudación.
- [ ] **D2** ⭐⭐ **Registro de notas.** Clase `Registro` con `String[] nombres` y `int[][] notas` (`n` estudiantes × 3 parciales). Métodos: promedio de un estudiante, promedio de un parcial, mejor estudiante y cantidad de aprobados.
- [ ] **D3** ⭐⭐⭐ **Tres en raya.** Clase `Tablero` con `char[][] casillas` de 3 × 3. Métodos: `boolean marcar(int f, int c, char jugador)`, `char ganador()` (`'X'`, `'O'` o `' '`) y `boolean lleno()`. Escribe un `main` para jugar entre dos personas.

---

## Parte E · Problemas integradores ⭐⭐⭐

Para cada problema: (1) modela las clases con un diagrama, (2) escribe los constructores, (3) implementa los métodos uno por uno y pruébalos en BlueJ, (4) haz la prueba de escritorio de los métodos con ciclos.

- [ ] **E1 · Colegio.** Un colegio tiene hasta **14** cursos. De cada curso se conoce el nombre, la cantidad de profesores y el número de estudiantes. Implementa las clases `Curso` y `Colegio` con:
  1. Constructor que permita registrar cualquier cantidad de cursos (hasta el máximo).
  2. Mostrar todos los cursos.
  3. El nombre del curso con más estudiantes.
  4. Añadir un curso nuevo.
  5. Buscar un curso por nombre.
  6. Eliminar un curso.

- [ ] **E2 · Búsqueda de huellas.** Se tiene una imagen de `N × N` con 0 (terreno plano) y 1 (hundimiento), y la huella de un animal como una matriz cuadrada más pequeña.
  1. Clase `Huella` con el nombre del animal y su matriz.
  2. Clase `Imagen` con la matriz de la imagen.
  3. Método que devuelva las posiciones (fila, columna de la esquina superior izquierda) donde la huella aparece **exactamente** en la imagen.
  4. Extra: que también la encuentre rotada 90°, 180° y 270° (usa `rotar90` de C7).

- [ ] **E3 · Filtro de imagen.** Dada una matriz `N × N` de números (brillo de cada píxel), con `N` múltiplo de 3:
  1. Redúcela a una matriz de **3 × 3**, donde cada casilla es el **promedio** del bloque de `N/3 × N/3` que le corresponde.
  2. Compara dos matrices de 3 × 3 con un puntaje: `promedio(menor) / promedio(mayor)`.
  3. Dibuja el diagrama de las clases que usaste.

- [ ] **E4 · Analizador de texto** (repaso de cadenas + arreglos). Clase `Analizador` que, dado un texto de hasta 1000 caracteres con palabras separadas por **un** espacio:
  1. Guarde en arreglos paralelos cada palabra y el tiempo en que se termina de leer (1 carácter = 1 unidad de tiempo).
  2. Dado un arreglo de palabras y otro de tiempos (que pueden venir **desordenados**), reconstruya la frase original.
  3. Extra: si falta una palabra (un hueco mayor a un espacio), muestre `-` en su lugar; si los tiempos son imposibles, devuelva `"ERROR"`.

---

## Autoevaluación final de la teoría

- [ ] Declarar, recorrer y mostrar una matriz con dos ciclos anidados.
- [ ] Calcular sumas por fila, por columna y de las diagonales.
- [ ] Recorrer regiones de una matriz cuadrada con la condición correcta.
- [ ] Usar una matriz o un arreglo de objetos como atributo de una clase.
- [ ] Modelar un problema grande en clases y programarlo método por método.

> [!quote] ¡Terminaste las 2 semanas de teoría! 🎉
> Ahora vienen las semanas de **resolución de ejercicios**. Vuelve a las autoevaluaciones de cada día ([[README|ruta]]) y refuerza los temas que no marcaste.
