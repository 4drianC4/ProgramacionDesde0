---
tipo: practica
dia: 7
semana: 2
tema: for, break, continue, ciclos anidados, figuras y series
tags: [java, intro-programacion, dia-07, practica]
---

# Práctica · Día 7

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 07 - Apuntes|apuntes del Día 7]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Proyecto de BlueJ: `Dia07`.
> - Para las figuras, haz **primero** la tabla de fila / espacios / símbolos en papel.

---

## Parte A · Seguir el código (en papel)

- [ ] **A1** ⭐ ¿Qué imprime cada ciclo?
  ```java
  for (int i = 10; i >= 0; i -= 3) System.out.print(i + " ");
  for (int i = 1; i <= 100; i *= 2) System.out.print(i + " ");
  for (int i = 0; i < 5; i++) { if (i == 3) break; System.out.print(i + " "); }
  for (int i = 0; i < 5; i++) { if (i == 3) continue; System.out.print(i + " "); }
  ```
- [ ] **A2** ⭐⭐ ¿Cuántas veces se ejecuta `cont++` en cada caso?
  ```java
  for (int i = 0; i < 4; i++) for (int j = 0; j < 5; j++) cont++;
  for (int i = 1; i <= 4; i++) for (int j = 1; j <= i; j++) cont++;
  for (int i = 1; i <= 4; i++) for (int j = i; j <= 4; j++) cont++;
  ```
- [ ] **A3** ⭐⭐ ¿Qué figura dibuja con `n = 4`?
  ```java
  for (int f = n; f >= 1; f--) {
      for (int c = 1; c <= f; c++) System.out.print("*");
      System.out.println();
  }
  ```
- [ ] **A4** ⭐ Reescribe con `for`:
  ```java
  int i = 20;
  while (i > 0) {
      System.out.println(i);
      i -= 4;
  }
  ```

> [!question]- Respuestas de la Parte A
> **A1:** `10 7 4 1` · `1 2 4 8 16 32 64` · `0 1 2` · `0 1 2 4`
>
> **A2:** 20 · 10 (1+2+3+4) · 10 (4+3+2+1)
>
> **A3:** triángulo invertido: `****`, `***`, `**`, `*`.
>
> **A4:** `for (int i = 20; i > 0; i -= 4) { System.out.println(i); }`

---

## Parte B · Repeticiones con `for`

- [ ] **B1** ⭐ `String tabla(int n)` → la tabla de multiplicar de `n` del 1 al 10.
- [ ] **B2** ⭐ `int sumaMultiplos3(int k)` → la suma de los `k` primeros múltiplos de 3.
- [ ] **B3** ⭐ `main` que lea **10** números y muestre su promedio.
- [ ] **B4** ⭐⭐ `main` que lea 10 números y muestre cuántos son pares, cuántos impares, cuántos múltiplos de 3, de 5 y de ambos.
- [ ] **B5** ⭐⭐ `String fibonacci(int n)` → los `n` primeros términos.
- [ ] **B6** ⭐⭐ `int sumaFibonacciPares(int limite)` → la suma de los términos pares de Fibonacci menores o iguales que `limite`.
- [ ] **B7** ⭐⭐ `double serie1(int n)` → $\frac{1}{2} + \frac{3}{4} + \frac{5}{8} + \frac{7}{16} + \dots$ (`n` términos).
- [ ] **B8** ⭐⭐ `String potencias3(int n)` → `1 3 9 27 81 …` (`n` términos).
- [ ] **B9** ⭐⭐ `int primerPrimoMayorQue(int n)` usando `break`.
- [ ] **B10** ⭐⭐⭐ `String primosEntre(int a, int b)` → todos los primos del intervalo (reutiliza `esPrimo` del [[Día 06 - Práctica|Día 6]]).

> [!tip]- Pista B7
> Los numeradores son impares (1, 3, 5…) y los denominadores, potencias de 2 (2, 4, 8…). Lleva dos variables que avancen en cada vuelta.

---

## Parte C · Figuras con asteriscos

Cada figura es un método `void dibujar…(int n)` que imprime con `System.out.print`. Ejemplos con `n = 4`:

- [ ] **C1** ⭐ Cuadrado de `n × n`.
- [ ] **C2** ⭐ Triángulo rectángulo:
  ```text
  *
  **
  ***
  ****
  ```
- [ ] **C3** ⭐⭐ Triángulo alineado a la derecha:
  ```text
     *
    **
   ***
  ****
  ```
- [ ] **C4** ⭐⭐ Pirámide:
  ```text
     *
    ***
   *****
  *******
  ```
- [ ] **C5** ⭐⭐ Cuadrado hueco:
  ```text
  ****
  *  *
  *  *
  ****
  ```
- [ ] **C6** ⭐⭐⭐ Rombo (pirámide + pirámide invertida).
- [ ] **C7** ⭐⭐⭐ **Pino.** Con la altura de la copa y la altura del tronco (el tronco tiene 3 asteriscos de ancho y va centrado). Con copa 4 y tronco 2:
  ```text
     *
    ***
   *****
  *******
    ***
    ***
  ```

---

## Parte D · Patrones numéricos

- [ ] **D1** ⭐ Con `n = 4`:
  ```text
  1
  12
  123
  1234
  ```
- [ ] **D2** ⭐⭐
  ```text
  1
  22
  333
  4444
  ```
- [ ] **D3** ⭐⭐ Las tablas de multiplicar del 1 al 9 en forma de cuadro (usa `"\t"` para alinear).
- [ ] **D4** ⭐⭐⭐ **Pirámide de números.** Cada fila sube y vuelve a bajar usando solo el último dígito (`% 10`). Con `n = 5`:
  ```text
      1
     232
    34543
   4567654
  567898765
  ```

> [!tip]- Pista D4
> En la fila `f` se imprimen `n - f` espacios, después los números de `f` a `2f - 1` y luego de `2f - 2` bajando hasta `f`, todos con `% 10`.

---

## Autoevaluación

Antes de pasar al [[Día 08 - Apuntes|Día 8]], comprueba que puedes:

- [ ] Escribir un `for` que cuente hacia adelante, hacia atrás y de `k` en `k`.
- [ ] Elegir entre `for`, `while` y `do-while` según el problema.
- [ ] Explicar qué hacen `break` y `continue`.
- [ ] Calcular cuántas veces se ejecuta el cuerpo de dos ciclos anidados.
- [ ] Dibujar triángulos y pirámides usando la tabla de fila / espacios / símbolos.
