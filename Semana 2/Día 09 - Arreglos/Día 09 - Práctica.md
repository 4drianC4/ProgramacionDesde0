---
tipo: practica
dia: 9
semana: 2
tema: Arreglos, búsqueda, arreglos paralelos y ordenamiento
tags: [java, intro-programacion, dia-09, practica]
---

# Práctica · Día 9

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 09 - Apuntes|apuntes del Día 9]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto (estilo examen).
> - Proyecto de BlueJ: `Dia09`. En BlueJ puedes pasar un arreglo como parámetro escribiéndolo así: `{4, 8, 15, 16, 23}`.

---

## Parte A · Seguir el código (en papel)

- [ ] **A1** ⭐ Con `int[] a = {3, 8, 1, 9, 4};`, ¿qué vale cada expresión?
  1. `a.length`
  2. `a[1] + a[3]`
  3. `a[a.length - 1]`
  4. `a[a[2]]`
  5. `a[5]`
- [ ] **A2** ⭐⭐ ¿Cómo queda el arreglo?
  ```java
  int[] b = new int[6];
  for (int i = 0; i < b.length; i++) {
      b[i] = i * i;
  }
  for (int i = 1; i < b.length; i++) {
      b[i] = b[i] + b[i - 1];
  }
  ```
- [ ] **A3** ⭐⭐ ¿Qué imprime? ¿Por qué?
  ```java
  public void cambiar(int x, int[] a) {
      x = 100;
      a[0] = 100;
  }
  // en main:
  int n = 5;
  int[] v = {5, 5, 5};
  objeto.cambiar(n, v);
  System.out.println(n + " " + v[0]);
  ```
- [ ] **A4** ⭐⭐ Haz la prueba de escritorio del método de la burbuja con `{4, 3, 2, 1}`. ¿Cuántos intercambios hace?

> [!question]- Respuestas de la Parte A
> **A1:** 1) `5` · 2) `17` · 3) `4` · 4) `8` (`a[2]` es 1, y `a[1]` es 8) · 5) error `ArrayIndexOutOfBoundsException`
>
> **A2:** primero `{0, 1, 4, 9, 16, 25}`; después las sumas acumuladas: `{0, 1, 5, 14, 30, 55}`.
>
> **A3:** `5 100`: el `int` se pasa como copia; el arreglo, como referencia al mismo arreglo.
>
> **A4:** queda `{1, 2, 3, 4}` con **6** intercambios (3 + 2 + 1).

---

## Parte B · Algoritmos básicos

Clase `Arreglos`, un método por ejercicio:

- [ ] **B1** ⭐ `int suma(int[] a)` y `double promedio(int[] a)`
- [ ] **B2** ⭐ `int maximo(int[] a)` y `int minimo(int[] a)`
- [ ] **B3** ⭐ `int contarPares(int[] a)`
- [ ] **B4** ⭐ `int buscar(int[] a, int x)` → posición o `-1`.
- [ ] **B5** ⭐⭐ `int contarMayoresAlPromedio(int[] a)`
- [ ] **B6** ⭐⭐ `int[] invertido(int[] a)` (devuelve uno nuevo) y `void invertir(int[] a)` (modifica el mismo).
- [ ] **B7** ⭐⭐ `boolean estaOrdenado(int[] a)`
- [ ] **B8** ⭐⭐ `int[] pares(int[] a)` → un arreglo nuevo solo con los pares (primero cuenta cuántos hay para saber el tamaño).
- [ ] **B9** ⭐⭐ `int segundoMayor(int[] a)`
- [ ] **B10** ⭐⭐ `int masRepetido(int[] a)`
- [ ] **B11** ⭐⭐⭐ `int[] rotarDerecha(int[] a, int k)` → rota `k` posiciones: `{1,2,3,4,5}` con 2 → `{4,5,1,2,3}`.

---

## Parte C · Lectura y arreglos paralelos

- [ ] **C1** ⭐ `main` que lea `n` y después `n` notas, y muestre el promedio, la mayor, la menor y cuántos aprobaron.
- [ ] **C2** ⭐⭐ `main` que lea los nombres y las notas de `n` estudiantes (arreglos paralelos) y muestre el nombre del mejor y la lista de los reprobados.
- [ ] **C3** ⭐⭐ Agrega a C2 un listado **ordenado por nota** de mayor a menor (al intercambiar notas, intercambia también los nombres).
- [ ] **C4** ⭐⭐ Agrega a C2 un listado **ordenado alfabéticamente** por nombre (usa `compareTo`).

---

## Parte D · Un arreglo como atributo

- [ ] **D1** ⭐⭐ Completa la clase `ListaNotas` de los apuntes con los métodos `double promedio()`, `int buscar(int nota)`, `String mostrar()` y `boolean insertar(int pos, int nota)` (desplaza a la derecha para hacer lugar).
- [ ] **D2** ⭐⭐⭐ **Agenda de contactos.** Clase `Agenda` con arreglos paralelos `nombres` y `telefonos` (máximo 50) y un contador. Métodos: `agregar`, `buscarTelefono(String nombre)`, `eliminar(String nombre)`, `cambiarTelefono(String nombre, String nuevo)` y `mostrar()`. Escribe un `main` con un menú `do-while`.

---

## Parte E · Problemas tipo examen ⭐⭐⭐

- [ ] **E1 · Cámara frigorífica.** De cada producto se registra: número de serie (`String`), vigencia (1 a 10 años), si es perecedero (`boolean`) y peso (kg). Con **arreglos paralelos**:
  1. Registra productos validando los datos y sin superar los **100 kg** de capacidad total.
  2. Guarda en un **arreglo nuevo** los números de serie de los productos perecederos con vigencia menor a 5 años.
  3. Muestra un reporte con todos los campos.

- [ ] **E2 · Lista de estudiantes.** Con estos datos en arreglos paralelos (nombre, parcial 1, parcial 2):

  | Nombre | P1 | P2 |
  |---|---|---|
  | Juan Romero | 55 | 64 |
  | Rosa Baldelomar | 42 | 86 |
  | Julio Quispe | 65 | 60 |
  | Luis Moreno | 33 | 58 |
  | Zulema Arteaga | 16 | 21 |

  1. Calcula el promedio de cada uno y su observación (`"Aprobado"` si es ≥ 51).
  2. Muestra los **dos** estudiantes con mejor promedio.
  3. Muestra el listado ordenado **por nombre** (ascendente).
  4. Muestra el listado ordenado **por promedio** (descendente).

---

## Autoevaluación

Antes de pasar al [[Día 10 - Apuntes|Día 10]], comprueba que puedes:

- [ ] Declarar, crear y recorrer un arreglo sin salirte de los índices.
- [ ] Calcular suma, promedio, máximo y mínimo, y buscar un elemento.
- [ ] Explicar por qué un método puede modificar el arreglo que recibe.
- [ ] Trabajar con arreglos paralelos sin "desordenar" los datos.
- [ ] Agregar y eliminar elementos usando un arreglo + contador.
- [ ] Ordenar con el método de la burbuja, ascendente y descendente.
