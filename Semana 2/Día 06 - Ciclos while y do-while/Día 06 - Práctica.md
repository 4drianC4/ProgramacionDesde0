---
tipo: practica
dia: 6
semana: 2
tema: while, do-while, contadores, acumuladores, centinelas y dígitos
tags: [java, intro-programacion, dia-06, practica]
---

# Práctica · Día 6

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 06 - Apuntes|apuntes del Día 6]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Proyecto de BlueJ: `Dia06`. Resuelve todo con `while` o `do-while` (el `for` lo vemos mañana).
> - En cada ejercicio con ciclo, haz la **prueba de escritorio** de las primeras vueltas y de la última.

---

## Parte A · Seguir el código (en papel)

- [ ] **A1** ⭐ ¿Qué imprime? ¿Cuántas vueltas da cada ciclo?
  ```java
  int i = 1;
  while (i <= 5) {
      System.out.print(i + " ");
      i += 2;
  }

  int j = 10;
  while (j < 5) {
      System.out.print(j + " ");
      j++;
  }

  int k = 10;
  do {
      System.out.print(k + " ");
      k++;
  } while (k < 5);
  ```
- [ ] **A2** ⭐⭐ Haz la prueba de escritorio con `n = 2024`. ¿Qué devuelve? ¿Qué problema resuelve?
  ```java
  public int misterio(int n) {
      int r = 0;
      while (n > 0) {
          int d = n % 10;
          if (d % 2 == 0) {
              r++;
          }
          n = n / 10;
      }
      return r;
  }
  ```
- [ ] **A3** ⭐⭐ Cada fragmento tiene un error. Encuéntralo y corrígelo:
  ```java
  // (a) debería sumar del 1 al 10
  int i = 1, s = 0;
  while (i < 10) { s += i; i++; }

  // (b) debería contar hacia atrás de 10 a 1
  int j = 10;
  while (j > 0) { System.out.println(j); j++; }

  // (c) debería multiplicar del 1 al 5
  int k = 1, p = 0;
  while (k <= 5) { p *= k; k++; }
  ```

> [!question]- Respuestas de la Parte A
> **A1:** `1 3 5` (3 vueltas) · nada (0 vueltas) · `10` (1 vuelta: el `do-while` siempre entra una vez).
>
> **A2:** devuelve `4`: **cuenta los dígitos pares** (4, 2, 0 y 2 son todos pares).
>
> **A3:** (a) `i <= 10`; (b) `j--` (con `j++` es infinito); (c) `p` debe empezar en `1`.

---

## Parte B · Del algoritmo a Java

Pasa a Java (como métodos que **devuelven**) estos algoritmos del [[Día 01 - Práctica#B.3 · Con contador, acumulador y repetición|Día 1]]. Compara tu prueba de escritorio de papel con lo que da BlueJ.

- [ ] **B1** ⭐ `int sumaHasta(int n)` → 1 + 2 + … + n.
- [ ] **B2** ⭐ `long factorial(int n)`
- [ ] **B3** ⭐ `int sumaPrimerosPares(int k)` → la suma de los `k` primeros pares.
- [ ] **B4** ⭐ `String multiplosDe7()` → los múltiplos de 7 entre 100 y 200, separados por espacios.
- [ ] **B5** ⭐⭐ `int cuadradoPorImpares(int n)` → suma los `n` primeros impares.
- [ ] **B6** ⭐⭐ `int multiplicarConSumas(int a, int b)`
- [ ] **B7** ⭐⭐ `String dividirConRestas(int a, int b)` → `"cociente 3, residuo 2"`.
- [ ] **B8** ⭐⭐ `double piGregory(int terminos)` → $4 \cdot (1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \dots)$.

> [!tip]- Pista B8
> Usa una variable `signo` que alterne entre `1` y `-1` en cada vuelta, y un denominador que avance de 2 en 2.

---

## Parte C · Dígitos

- [ ] **C1** ⭐ `int contarDigitos(int n)`
- [ ] **C2** ⭐ `int sumarDigitos(int n)`
- [ ] **C3** ⭐⭐ `int invertir(int n)` y `boolean esEspejo(int n)`.
- [ ] **C4** ⭐⭐ `int mayorDigito(int n)`
- [ ] **C5** ⭐⭐ `int rotarDerecha(int n)` → 12345 → 51234 (para cualquier cantidad de cifras).
- [ ] **C6** ⭐⭐ `int rotarIzquierda(int n)` → 12345 → 23451.
- [ ] **C7** ⭐⭐⭐ `boolean esArmstrong(int n)` → la suma de cada dígito elevado a la cantidad de dígitos es igual al número ($153 = 1^3 + 5^3 + 3^3$).
- [ ] **C8** ⭐⭐⭐ `String aBinario(int n)` → `13` → `"1101"`.

> [!tip]- Pista C5
> Separa el último dígito (`n % 10`) y el resto (`n / 10`). El último dígito pasa al frente multiplicado por $10^{(\text{cifras} - 1)}$. Usa `contarDigitos`.

---

## Parte D · Divisores, centinelas y banderas

- [ ] **D1** ⭐ `int cantidadDivisores(int n)`
- [ ] **D2** ⭐ `boolean esPrimo(int n)` (con bandera).
- [ ] **D3** ⭐⭐ `boolean esPerfecto(int n)` → igual a la suma de sus divisores menores que él (6, 28).
- [ ] **D4** ⭐⭐ `int mcd(int a, int b)` con el algoritmo de Euclides: mientras `b != 0`, `(a, b) ← (b, a % b)`.
- [ ] **D5** ⭐⭐ `main` que lea números hasta que se ingrese `0` y muestre cuántos fueron positivos, cuántos negativos, la suma y el promedio.
- [ ] **D6** ⭐⭐ `main` que lea números hasta `-1` y muestre el **mayor** y el **menor**.

---

## Parte E · `do-while`

- [ ] **E1** ⭐ `main` que pida una nota y **la vuelva a pedir** mientras no esté entre 0 y 100.
- [ ] **E2** ⭐⭐ **Cajero automático.** Clase `Cuenta` (del Día 4) + `main` con un menú: 1. Depositar · 2. Retirar · 3. Ver saldo · 0. Salir. Se repite hasta elegir 0, y no permite retirar más que el saldo.
- [ ] **E3** ⭐⭐⭐ **Adivina el número.** La computadora elige un número en $[1, 100]$. El usuario intenta adivinarlo; el programa responde `"Más alto"` o `"Más bajo"` hasta acertar, y al final muestra cuántos intentos usó.
- [ ] **E4** ⭐⭐⭐ **¡Alcanza el número!** (completo). Retoma la clase `Juego` del [[Día 05 - Práctica#Parte D · Problemas tipo examen ⭐⭐⭐|Día 5]] y escribe un `main` que haga jugar al humano contra la computadora, por turnos, hasta que alguien gane o haya empate.

---

## Autoevaluación

Antes de pasar al [[Día 07 - Apuntes|Día 7]], comprueba que puedes:

- [ ] Escribir un `while` y un `do-while`, y explicar en qué se diferencian.
- [ ] Señalar la inicialización, la condición y la actualización de cualquier ciclo.
- [ ] Hacer la prueba de escritorio de un ciclo y detectar si da una vuelta de más o de menos.
- [ ] Usar contadores, acumuladores, centinelas y banderas.
- [ ] Recorrer los dígitos de un número con `% 10` y `/ 10`.
