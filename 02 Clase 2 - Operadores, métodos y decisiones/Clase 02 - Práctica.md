---
tipo: practica
clase: 2
semanas: [3, 4]
tema: Expresiones, métodos, Scanner e if-else
tags: [java, intro-programacion, clase-02, practica]
---

# Práctica · Clase 2

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Clase 02 - Apuntes|apuntes de la Clase 2]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto (nivel examen).
> - Las partes A y B se hacen en **papel** (tienen respuestas para autoevaluarte). Desde la parte C se programa en **BlueJ** (proyecto `Clase02`).
> - **Regla del curso:** la lógica va en métodos que **devuelven** su resultado (`return`). Solo `main` lee con `Scanner` e imprime.
> - Todavía **no** usamos ciclos (`while`, `for`): todo se resuelve con operadores, métodos e `if`.

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
- [ ] **B3** ⭐⭐ Haz la prueba de escritorio con `n = 2468` e indica qué devuelve el método. ¿Qué problema resuelve?
  ```java
  public int misterio(int n) {
      int u = n % 10;
      int d = n / 10 % 10;
      int c = n / 100 % 10;
      int m = n / 1000;
      return u * 1000 + d * 100 + c * 10 + m;
  }
  ```
- [ ] **B4** ⭐⭐ ¿Qué devuelve `clasifica(15)`, `clasifica(9)`, `clasifica(10)` y `clasifica(7)`?
  ```java
  public String clasifica(int n) {
      String r;
      if (n % 3 == 0 && n % 5 == 0) {
          r = "AMBOS";
      } else if (n % 3 == 0) {
          r = "TRES";
      } else if (n % 5 == 0) {
          r = "CINCO";
      } else {
          r = "NINGUNO";
      }
      return r;
  }
  ```
- [ ] **B5** ⭐⭐ Este código **compila**, pero tiene **tres** errores de lógica. Encuéntralos:
  ```java
  public String saludo(String nombre, int hora) {
      String r = "";
      if (nombre == "Ana");
      {
          r = "Hola Ana. ";
      }
      if (hora < 12)
          r = r + "Buenos días";
          r = r + "!";
      return r;
  }
  ```

> [!question]- Respuestas de la Parte B
> **B1:** `y = 5` y `x = 6`; luego `++x` → `x = 7`, `z = 7 + 5 = 12` y `y` pasa a `4`; finalmente `x = 7 + 4 = 11`. Resultado: **x = 11, y = 4, z = 12**.
>
> **B2:** `Resultado: 72` · `Resultado: 9` · `9 es el resultado` · `3 y 1` · `H`
>
> **B3:** devuelve `8642`: **invierte** un número de 4 cifras.
>
> **B4:** `AMBOS`, `TRES`, `CINCO`, `NINGUNO`.
>
> **B5:** (1) `==` con `String` → usar `nombre.equals("Ana")`; (2) el `;` después del `if` hace que el bloque se ejecute siempre; (3) sin llaves, `r = r + "!";` no pertenece al segundo `if` y se ejecuta siempre, aunque la sangría haga creer lo contrario.

---

## Parte C · Métodos (BlueJ)

Crea la clase `Calculos` y agrega un método por ejercicio. Prueba cada uno con clic derecho sobre un objeto.

- [ ] **C1** ⭐ `public double areaRectangulo(double base, double altura)`
- [ ] **C2** ⭐ `public double promedio(double n1, double n2, double n3)`
- [ ] **C3** ⭐ `public double celsiusAFahrenheit(double c)`
- [ ] **C4** ⭐ `public boolean esPar(int n)` (en **una** línea, sin `if`)
- [ ] **C5** ⭐ `public boolean esMultiplo(int n, int m)` → `true` si `n` es múltiplo de `m`.
- [ ] **C6** ⭐⭐ `public int sumaDigitos(int n)` para un número de **3** cifras (427 → 13).
- [ ] **C7** ⭐⭐ `public String convertirSegundos(int seg)` → `"1 h 2 min 5 s"` para 3725.
- [ ] **C8** ⭐⭐ `public double hipotenusa(double a, double b)` usando `Math.sqrt` y `Math.pow`.
- [ ] **C9** ⭐⭐ `public int aleatorio(int inf, int sup)` → entero aleatorio en $[inf, sup)$. Pruébalo varias veces.
- [ ] **C10** ⭐⭐ `public char siguienteLetra(char c)` → la letra siguiente (`'a'` → `'b'`).
- [ ] **C11** ⭐⭐ `public double precioFinal(double precio, int cantidad)` → reutiliza un método `private double subtotal(…)` y suma un 13 % de IVA.
- [ ] **C12** ⭐⭐ Agrega a la clase `Estudiante` de la Clase 1 los métodos `promedio()` y `estaAprobado()` que usen sus atributos.

> [!tip]- Pista C7
> `seg / 3600` son las horas. `seg % 3600` es lo que sobra; de ahí sacas los minutos con `/ 60` y los segundos con `% 60`.

> [!tip]- Pista C11
> Un método `private` no aparece en el menú del objeto de BlueJ, pero sí lo puede usar otro método de la **misma** clase.

---

## Parte D · Entrada de datos con `Scanner`

- [ ] **D1** ⭐ Agrega un `main` a `Calculos` que lea la base y la altura, llame a `areaRectangulo` y muestre: `El área es: 12.5`.
- [ ] **D2** ⭐ Programa que lea el nombre (`nextLine`) y la edad (`nextInt`) y muestre: `Hola Ana, el próximo año tendrás 21 años.`
- [ ] **D3** ⭐⭐ Programa que lea un `double` con decimales. Pruébalo escribiendo `4.5` y luego `4,5`. ¿Qué pasa? Arréglalo con `useLocale`.
- [ ] **D4** ⭐⭐ Programa que lea primero la edad (`nextInt`) y luego el nombre (`nextLine`). ¿Qué falla? Arréglalo.
- [ ] **D5** ⭐⭐ Programa que lea un `char` (con `next().charAt(0)`) y muestre su código ASCII.

---

## Parte E · Decisiones con `if`

Para cada ejercicio: un método con la lógica (que **devuelve**), un `main` que lea y muestre, y una **tabla de pruebas** con un dato por cada camino del `if`.

- [ ] **E1** ⭐ `signo(int n)` → `"POSITIVO"`, `"NEGATIVO"` o `"CERO"`.
- [ ] **E2** ⭐ `mayor(int a, int b)` y luego `mayor(int a, int b, int c)` reutilizando el primero.
- [ ] **E3** ⭐ `evaluarNota(double nota)` → `"NOTA INVÁLIDA"`, `"APROBADO"` (≥ 51), `"CASO ESPECIAL"` (de 50 a menos de 51) o `"REPROBADO"`.
- [ ] **E4** ⭐ `esBisiesto(int anio)`.
- [ ] **E5** ⭐⭐ `tipoTriangulo(double a, double b, double c)` → `"NO ES TRIÁNGULO"`, `"EQUILÁTERO"`, `"ISÓSCELES"` o `"ESCALENO"`. (Tres lados forman un triángulo si cada uno es menor que la suma de los otros dos.)
- [ ] **E6** ⭐⭐ `tipoCaracter(char c)` → `"VOCAL"`, `"CONSONANTE"`, `"DÍGITO"` u `"OTRO"` (considera mayúsculas y minúsculas).
- [ ] **E7** ⭐⭐ `tarifaTaxi(double km)`: Bs. 10 la bajada de bandera, que incluye los 2 primeros km; Bs. 3 cada km adicional; con un 20 % de recargo si el viaje pasa de 15 km.
- [ ] **E8** ⭐⭐ `calcularIMC(double peso, double talla)` y `clasificarIMC(double imc)` → bajo peso (< 18.5), normal (< 25), sobrepeso (< 30), obesidad.
- [ ] **E9** ⭐⭐ `ordenarTres(int a, int b, int c)` → devuelve un `String` con los tres números ordenados de menor a mayor.
- [ ] **E10** ⭐⭐ `cajero(double saldo, double monto)` → `"Monto inválido"` si `monto <= 0`, `"Saldo insuficiente"` si `monto > saldo`, o `"Retiro exitoso. Nuevo saldo: …"`.
- [ ] **E11** ⭐⭐ `resolverCuadratica(double a, double b, double c)` → las raíces reales, `"RAÍZ DOBLE: …"` o `"SIN RAÍCES REALES"` según el discriminante.
- [ ] **E12** ⭐⭐⭐ `diaSiguiente(int d, int m, int a)` → la fecha del día siguiente como `"d/m/a"` (usa `esBisiesto`).

> [!tip]- Pista E9
> Con tres números hay 6 órdenes posibles. Otra idea: el menor es `Math.min(a, Math.min(b, c))`, el mayor es `Math.max(…)`, y el del medio es `a + b + c - menor - mayor`.

> [!tip]- Pista E12
> Primero calcula cuántos días tiene el mes `m` (28/29, 30 o 31). Si `d` es el último día del mes, pasas al día 1 del mes siguiente; y si además es diciembre, al año siguiente.

---

## Parte F · Problemas tipo examen ⭐⭐⭐

Problemas con el estilo de los exámenes de la materia, resueltos con lo que sabes hasta ahora (sin ciclos ni arreglos).

- [ ] **F1 · Cifrado César (una letra).** Cada letra se reemplaza por la que está `N` posiciones más adelante en el alfabeto inglés, dando la vuelta al llegar a la `z` (con N = 5: `'c'` → `'h'`, `'z'` → `'e'`).
  1. `public char cifrar(char c, int n)`
  2. `public char descifrar(char c, int n)`
  > [!tip]- Pista
  > Convierte la letra en su posición 0–25 con `c - 'a'`, súmale `n`, aplica `% 26` y vuelve a convertirla con `(char) ('a' + pos)`. Para descifrar, suma `26 - n` en lugar de restar (así evitas el `%` de números negativos).

- [ ] **F2 · ¡Alcanza el número!** Dos jugadores parten de 0 y, por turnos, suman un incremento de **1 a 4**. Gana quien llega **exactamente** al número objetivo; si alguien lo pasa, es empate. Crea la clase `Juego` con los atributos `objetivo` y `acumulado`:
  1. El constructor elige un objetivo aleatorio en $[10, 60)$ y pone `acumulado` en 0.
  2. `public boolean esIncrementoValido(int inc)`
  3. `public String jugar(int inc)`: si el incremento no es válido, devuelve `"Incremento inválido"`; si no, actualiza `acumulado` y devuelve `"Acumulado: X"`, `"¡GANASTE!"` o `"EMPATE: te pasaste"`.
  4. ⭐ Extra: `public int jugadaComputadora()` que devuelva el incremento "inteligente": el que deja el acumulado en un número tal que `(objetivo - acumulado) % 5 == 0`, o `1` si no es posible.

- [ ] **F3 · ¿Mayor o menor?** La computadora piensa un número secreto entre 1 y 100. En las preguntas **impares** se responde `true` si el número dado es **menor o igual** que el secreto; en las **pares**, `true` si es **mayor**. Crea la clase `Adivina` con `numeroSecreto` (aleatorio) y `partida` (contador de preguntas), y el método `public boolean darNumero(int numero)`.

- [ ] **F4 · Cámara frigorífica.** La cámara admite como máximo **100 kg**. Crea la clase `Camara` con el atributo `pesoActual` y el método `public String ingresar(String serie, int vigencia, boolean perecedero, double peso)` que:
  - rechace el producto si `vigencia` no está entre 1 y 10, o si `peso <= 0`;
  - rechace el producto si no cabe;
  - si lo acepta, actualice `pesoActual` y agregue `" (REVISAR PRONTO)"` al mensaje cuando sea perecedero con vigencia menor a 5 años.

- [ ] **F5 · Rotar dígitos.** Para un número de **4** cifras:
  1. `rotarDerecha(int n)` → 1234 → 4123
  2. `rotarIzquierda(int n)` → 1234 → 2341
  3. `esEspejo(int n)` → `true` si se lee igual al revés (1221).

- [ ] **F6 · Masitas en cajas.** Una caja rectangular tiene `base × altura`. Se quiere poner una masita circular de radio `r`; cabe si su diámetro no supera ni la base ni la altura. Crea la clase `Caja` con `base`, `altura` y `masitas` (contador), y el método `public String ponerMasita(double r)` que devuelva `"Masita ubicada"` (y cuente la masita) o `"No cabe"`. ⭐ Extra: agrega el atributo `areaOcupada`, súmale $\pi r^2$ cada vez que ubiques una masita y escribe `public double areaUsada()`.

---

## Autoevaluación

Antes de pasar a las sesiones de ejercicios, comprueba que puedes:

- [ ] Predecir el resultado de `/` y `%` con enteros y con decimales.
- [ ] Explicar la diferencia entre `x++` y `++x`.
- [ ] Traducir cualquier condición en español a una expresión con `&&`, `||` y `!`.
- [ ] Escribir un método con parámetros y `return`, y explicar qué significa `void`.
- [ ] Explicar por qué `main` no puede llamar directamente a un método sin `static`.
- [ ] Leer `int`, `double`, `String` y `char` con `Scanner`.
- [ ] Escribir un `if / else if / else` y elegir datos de prueba para **cada** camino.

> [!quote] Lo que viene
> En las semanas de ejercicios se combinan estos temas. El siguiente bloque teórico de la materia son los **ciclos** (`while`, `do-while`, `for`), que permiten llevar a Java los algoritmos con repetición de la [[Clase 01 - Práctica#B.3 · Con contador, acumulador y repetición|Parte B.3 de la Clase 1]].
