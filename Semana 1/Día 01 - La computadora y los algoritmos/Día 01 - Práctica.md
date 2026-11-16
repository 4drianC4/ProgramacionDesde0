---
tipo: practica
dia: 1
semana: 1
tema: Computadora, binario, algoritmos y prueba de escritorio
tags: [java, intro-programacion, dia-01, practica]
---

# Práctica · Día 1

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 01 - Apuntes|apuntes del Día 1]].
> - Marca cada ejercicio cuando lo termines (los checkboxes funcionan en Obsidian).
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Abre las **pistas** solo después de intentarlo al menos 10 minutos.
> - Toda esta práctica se hace en **papel**: todavía no usamos la computadora.

---

## Parte A · La computadora y el binario

- [ ] **A1** ⭐ Clasifica como **hardware** o **software**: teclado, BlueJ, memoria RAM, Windows, disco SSD, tu programa `Ejemplo.java`, la JVM, el procesador.
- [ ] **A2** ⭐ Convierte a binario: **13**, **26**, **45**, **100**.
- [ ] **A3** ⭐ Convierte a decimal: `1010`, `11111`, `100000`, `1100100`.
- [ ] **A4** ⭐⭐ ¿Cuántos valores distintos se pueden representar con 8 bits? ¿Y con 16? Relaciona tu respuesta con los rangos de `byte` y `short`.
- [ ] **A5** ⭐⭐ Explica con tus palabras qué hacen el **compilador** y la **JVM**, y por qué un `.class` compilado en Windows funciona en Linux.
- [ ] **A6** ⭐ Un programa compila sin errores pero muestra un resultado incorrecto. ¿Qué tipo de error tiene? ¿Cómo lo detectarías?

> [!question]- Respuestas de la Parte A (para autoevaluarte)
> - **A2:** 13 = `1101` · 26 = `11010` · 45 = `101101` · 100 = `1100100`
> - **A3:** `1010` = 10 · `11111` = 31 · `100000` = 32 · `1100100` = 100
> - **A4:** $2^8 = 256$ (de −128 a 127 en `byte`) · $2^{16} = 65\,536$ (de −32 768 a 32 767 en `short`).
> - **A6:** un **error de lógica**. Se detecta con la **prueba de escritorio** y probando con varios datos.

---

## Parte B · Algoritmos y prueba de escritorio

Para **cada** ejercicio: (1) escribe el análisis (entradas, salidas, proceso), (2) el algoritmo en pseudocódigo numerado y (3) la **prueba de escritorio** con al menos un juego de datos.

### B.1 · Secuenciales (sin condiciones ni repeticiones)

- [ ] **B1** ⭐ Leer el radio de un círculo y mostrar su área y su perímetro.
- [ ] **B2** ⭐ Leer dos notas parciales y mostrar el promedio.
- [ ] **B3** ⭐ Leer una temperatura en °C y mostrarla en °F ($F = C \cdot 9/5 + 32$).
- [ ] **B4** ⭐⭐ Leer una cantidad de segundos y mostrarla en horas, minutos y segundos (por ejemplo, 3725 → 1 h 2 min 5 s).
- [ ] **B5** ⭐⭐ Leer los valores de `A` y `B` e **intercambiarlos** (al final `A` debe tener el valor de `B` y viceversa).

### B.2 · Con condiciones

- [ ] **B6** ⭐ Leer un número y mostrar si es positivo, negativo o cero.
- [ ] **B7** ⭐ Leer dos números `A` y `B` y guardar en `M` el mayor.
- [ ] **B8** ⭐⭐ Leer una nota (0–100) y mostrar **APROBADO** si es ≥ 51, **REPROBADO** si es < 50 y **CASO ESPECIAL** si está entre 50 y 51. Elige los datos de prueba para cubrir **todos** los casos.

### B.3 · Con contador, acumulador y repetición

- [ ] **B9** ⭐ Mostrar la suma de los números del 1 al 10.
- [ ] **B10** ⭐ Mostrar el factorial de un número `n` entero positivo.
- [ ] **B11** ⭐ Mostrar la suma de los 20 primeros números pares.
- [ ] **B12** ⭐ Mostrar la suma de los 10 primeros múltiplos de 3.
- [ ] **B13** ⭐⭐ Generar y mostrar los múltiplos de 7 entre 100 y 200.
- [ ] **B14** ⭐⭐ Calcular el cuadrado de `N` sumando los `N` primeros impares (si N = 4: 1 + 3 + 5 + 7 = 16).
- [ ] **B15** ⭐⭐ Leer 10 números y mostrar cuántos son positivos, cuántos negativos y cuántos ceros.
- [ ] **B16** ⭐⭐ Leer 10 números y mostrar el mayor de ellos.
- [ ] **B17** ⭐⭐ Multiplicar `A × B` usando **solo sumas** sucesivas.
- [ ] **B18** ⭐⭐⭐ Dividir `A ÷ B` (con `A > B`) usando **solo restas** sucesivas. Mostrar el cociente y el residuo.
- [ ] **B19** ⭐⭐⭐ Leer `N` y mostrar los `N` primeros términos de la serie de Fibonacci: 0, 1, 1, 2, 3, 5, 8, 13, 21…

> [!tip]- Pista B5 (intercambio)
> Si haces `A ← B` y después `B ← A`, pierdes el valor original de `A`. Necesitas una variable **auxiliar**.

> [!tip]- Pista B4
> Usa `div` (división entera) y `mod` (residuo): las horas son `seg div 3600`; lo que sobra es `seg mod 3600`.

> [!tip]- Pista B18
> Cuenta cuántas veces puedes restar `B` de `A` mientras `A ≥ B`. Lo que queda en `A` al final es el residuo.

---

## Parte C · Leer algoritmos ajenos

Para cada algoritmo: haz la **prueba de escritorio** con los datos indicados, **describe qué problema resuelve** y busca un dato que lo haga **fallar** (si existe).

- [ ] **C1** ⭐⭐ Prueba con `N = 123456`.
  ```text
  1. Leer N
  2. C ← 0
  3. N ← N div 10
  4. C ← C + 1
  5. Si N > 0 Entonces Ir a 3
  6. Mostrar C
  7. FIN
  ```
- [ ] **C2** ⭐⭐ Prueba con `A = 3, B = 5` y después con `A = 5, B = 3`. ¿Qué pasa si `B = 0`?
  ```text
  1. Leer A, B
  2. C ← 0 : S ← 0
  3. S ← S + A
  4. C ← C + 1
  5. Si C < B Entonces Ir a 3
  6. Mostrar S
  7. FIN
  ```
- [ ] **C3** ⭐⭐ Prueba con `P = 8, Q = 2` y después con `P = 8, Q = 3`. ¿Qué pasa si `P = Q`?
  ```text
  1. Leer P, Q
  2. C ← 0
  3. Si P > Q Entonces May ← P : Men ← Q
  4. Si Q > P Entonces May ← Q : Men ← P
  5. May ← May – Men : C ← C + 1
  6. Si May >= Men Entonces Ir a 5
  7. Mostrar C
  8. FIN
  ```
- [ ] **C4** ⭐⭐⭐ Prueba con `N = 6`, `N = 8` y `N = 28`. Completa los mensajes del paso 6.
  ```text
  1. Leer N
  2. C ← 0 : S ← 0
  3. C ← C + 1
  4. Si N mod C = 0 Entonces S ← S + C
  5. Si C < N – 1 Entonces Ir a 3
  6. Si S = N Entonces Mostrar "Sí es ……" Sino Mostrar "No es ……"
  7. FIN
  ```

> [!tip]- Pista C4
> En el paso 4, `S` acumula los **divisores** de `N` (sin contar al propio `N`). ¿Qué nombre reciben los números iguales a la suma de sus divisores?


---

## Autoevaluación

Antes de pasar al [[Día 02 - Apuntes|Día 2]], comprueba que puedes:

- [ ] Explicar entrada → proceso → salida y la diferencia entre hardware y software.
- [ ] Convertir números entre decimal y binario.
- [ ] Explicar qué hacen el compilador y la JVM.
- [ ] Escribir un algoritmo con contador, acumulador y repetición.
- [ ] Hacer la prueba de escritorio de cualquier algoritmo de la Parte C.

> [!quote] Para los exámenes
> En los exámenes de la materia se suele pedir el programa **junto con su prueba de escritorio**. Practícala desde hoy.
