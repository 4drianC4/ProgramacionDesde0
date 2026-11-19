---
tipo: practica
dia: 3
semana: 1
tema: Operadores, expresiones, casting y Math
tags: [java, intro-programacion, dia-03, practica]
---

# Práctica · Día 3

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 03 - Apuntes|apuntes del Día 3]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Las partes A y B se hacen en **papel** y tienen respuestas plegadas para que te corrijas. La parte C se programa en **BlueJ** (proyecto `Dia03`).

---

## Parte A · Evaluar expresiones (en papel)

- [ ] **A1** ⭐ Escribe el **valor** y el **tipo** del resultado:
  1. `17 / 5`
  2. `17 % 5`
  3. `17.0 / 5`
  4. `(double) 17 / 5`
  5. `(double) (17 / 5)`
  6. `(int) 9.99`
  7. `5 % 7`
  8. `-7 % 3`
  9. `2 + 3 * 4 - 6 / 2`
  10. `(2 + 3) * (4 - 6) / 2`

- [ ] **A2** ⭐⭐ Con `int a = 5, b = 3, c = 8;` y `boolean p = true, q = false;`, evalúa:
  1. `a > b && c > a`
  2. `a > b && c < a`
  3. `a == 5 || b == 5`
  4. `!(a > b)`
  5. `a + b == c`
  6. `p && !q`
  7. `!p || q && a < b`
  8. `c % a == b && a % 2 != 0`
  9. `a * 2 > c || b * 3 < c && p`

- [ ] **A3** ⭐⭐ Escribe la **expresión Java** (que devuelva `boolean`) para cada condición:
  1. `n` es par.
  2. `n` es múltiplo de 3 **y** de 5.
  3. `edad` está entre 18 y 65, ambos incluidos.
  4. `nota` está **fuera** del rango 0–100.
  5. `c` es una letra minúscula.
  6. `c` es un dígito.
  7. `anio` es bisiesto (divisible entre 4 y no entre 100, o divisible entre 400).
  8. `x` es positivo y termina en 0.

- [ ] **A4** ⭐⭐ Escribe la expresión Java para cada fórmula matemática:
  1. $\dfrac{a + b}{2}$
  2. $\sqrt{b^2 - 4ac}$
  3. $\dfrac{-b + \sqrt{b^2 - 4ac}}{2a}$
  4. Área de un círculo: $\pi r^2$
  5. Distancia entre dos puntos: $\sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$

> [!question]- Respuestas de la Parte A
> **A1:** 1) `3` int · 2) `2` int · 3) `3.4` double · 4) `3.4` double · 5) `3.0` double · 6) `9` int · 7) `5` int · 8) `-1` int · 9) `11` int · 10) `-5` int
>
> **A2:** 1) true · 2) false · 3) true · 4) false · 5) true · 6) true · 7) false (`&&` va antes que `||`: `false || (false && false)`) · 8) true · 9) true (`10 > 8` ya es true)
>
> **A3:** 1) `n % 2 == 0` · 2) `n % 3 == 0 && n % 5 == 0` · 3) `edad >= 18 && edad <= 65` · 4) `nota < 0 || nota > 100` · 5) `c >= 'a' && c <= 'z'` · 6) `c >= '0' && c <= '9'` · 7) `(anio % 4 == 0 && anio % 100 != 0) || anio % 400 == 0` · 8) `x > 0 && x % 10 == 0`
>
> **A4:** 1) `(a + b) / 2.0` · 2) `Math.sqrt(b*b - 4*a*c)` · 3) `(-b + Math.sqrt(b*b - 4*a*c)) / (2*a)` · 4) `Math.PI * r * r` · 5) `Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2))`

---

## Parte B · Seguir el código (en papel)

- [ ] **B1** ⭐⭐ ¿Qué valores tienen `x`, `y` y `z` al final?
  ```java
  int x = 5;
  int y = x++;
  int z = ++x + y--;
  x += y;
  ```
- [ ] **B2** ⭐⭐ ¿Qué imprime?
  ```java
  int a = 7, b = 2;
  System.out.println("Resultado: " + a + b);
  System.out.println("Resultado: " + (a + b));
  System.out.println(a + b + " es el resultado");
  System.out.println(a / b + " y " + a % b);
  System.out.println((char) ('A' + a));
  ```
- [ ] **B3** ⭐⭐ Haz la prueba de escritorio con `n = 2468`. ¿Qué valor queda en `r`? ¿Qué hace este código?
  ```java
  int u = n % 10;
  int d = n / 10 % 10;
  int c = n / 100 % 10;
  int m = n / 1000;
  int r = u * 1000 + d * 100 + c * 10 + m;
  ```
- [ ] **B4** ⭐⭐ Con `double precio = 45.75;` y `int cantidad = 3;`, ¿qué guarda cada variable?
  ```java
  double total   = precio * cantidad;
  int    entero  = (int) total;
  long   redondo = Math.round(total);
  int    bs      = (int) precio;
  int    ctvs    = (int) Math.round((precio - bs) * 100);
  ```

> [!question]- Respuestas de la Parte B
> **B1:** `y = 5` y `x = 6`; luego `++x` → `x = 7`, `z = 7 + 5 = 12` y `y` pasa a `4`; finalmente `x = 7 + 4 = 11`. Resultado: **x = 11, y = 4, z = 12**.
>
> **B2:** `Resultado: 72` · `Resultado: 9` · `9 es el resultado` · `3 y 1` · `H`
>
> **B3:** `r = 8642`: **invierte** un número de 4 cifras.
>
> **B4:** `total = 137.25` · `entero = 137` · `redondo = 137` · `bs = 45` · `ctvs = 75`

---

## Parte C · Expresiones en BlueJ

Crea la clase `Expresiones`. Cada ejercicio es un método de **una sola línea** con `return`, como el método de la plantilla del [[Día 02 - Apuntes#3. Estructura de una clase|Día 2]]. Pruébalos con clic derecho sobre un objeto.

```java
public double areaRectangulo(double base, double altura) {
    return base * altura;
}
```

- [ ] **C1** ⭐ `public double promedio(double n1, double n2, double n3)`
- [ ] **C2** ⭐ `public double celsiusAFahrenheit(double c)`
- [ ] **C3** ⭐ `public boolean esPar(int n)`
- [ ] **C4** ⭐ `public boolean esMultiplo(int n, int m)` → `true` si `n` es múltiplo de `m`.
- [ ] **C5** ⭐ `public boolean enRango(double nota)` → `true` si la nota está entre 0 y 100.
- [ ] **C6** ⭐⭐ `public int sumaDigitos(int n)` para un número de **3** cifras (427 → 13).
- [ ] **C7** ⭐⭐ `public int invertir(int n)` para un número de **3** cifras (427 → 724).
- [ ] **C8** ⭐⭐ `public double hipotenusa(double a, double b)` usando `Math.sqrt` y `Math.pow`.
- [ ] **C9** ⭐⭐ `public int aleatorio(int inf, int sup)` → entero aleatorio en $[inf, sup)$. Pruébalo varias veces.
- [ ] **C10** ⭐⭐ `public char siguienteLetra(char c)` → la letra siguiente (`'a'` → `'b'`).
- [ ] **C11** ⭐⭐ `public boolean esBisiesto(int anio)`
- [ ] **C12** ⭐⭐ `public int horaDespues(int hora, int horas)` → la hora del reloj (0–23) después de sumar `horas` (22 + 5 → 3).
- [ ] **C13** ⭐⭐⭐ `public char cifrarCesar(char c, int n)` → la letra minúscula `n` posiciones más adelante, dando la vuelta al llegar a la `z` (`'z'` con 5 → `'e'`).

> [!tip]- Pista C7
> Saca las unidades, las decenas y las centenas con `%` y `/`, y vuelve a armar el número con las posiciones cambiadas.

> [!tip]- Pista C13
> Convierte la letra en su posición 0–25 con `c - 'a'`, súmale `n`, aplica `% 26` y vuelve a convertirla: `(char) ('a' + pos)`.

---

## Autoevaluación

Antes de pasar al [[Día 04 - Apuntes|Día 4]], comprueba que puedes:

- [ ] Predecir el resultado de `/` y `%` con enteros y con decimales.
- [ ] Explicar la diferencia entre `x++` y `++x`.
- [ ] Traducir cualquier condición en español a una expresión con `&&`, `||` y `!`.
- [ ] Evaluar una expresión paso a paso respetando la precedencia.
- [ ] Convertir tipos con *casting* y usar `Math.sqrt`, `Math.pow` y `Math.random`.
