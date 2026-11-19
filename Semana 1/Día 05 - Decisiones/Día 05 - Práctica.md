---
tipo: practica
dia: 5
semana: 1
tema: if, else if, ternario y switch
tags: [java, intro-programacion, dia-05, practica]
---

# Práctica · Día 5

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 05 - Apuntes|apuntes del Día 5]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto (estilo examen).
> - Proyecto de BlueJ: `Dia05`.
> - Para cada ejercicio de las partes B a D: un método con la lógica (que **devuelve**), un `main` que lea y muestre, y una **tabla de pruebas** con un dato por cada camino del `if`.
> - Todavía **no** usamos ciclos: todo se resuelve con operadores, métodos y decisiones.

---

## Parte A · Seguir el código (en papel)

- [ ] **A1** ⭐⭐ ¿Qué devuelve `clasifica(15)`, `clasifica(9)`, `clasifica(10)` y `clasifica(7)`?
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
- [ ] **A2** ⭐⭐ Este código **compila**, pero tiene **tres** errores de lógica. Encuéntralos:
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
- [ ] **A3** ⭐⭐ ¿Qué devuelve `tipo(2)` y `tipo(5)`? ¿Qué error tiene este `switch`?
  ```java
  public String tipo(int n) {
      String r = "";
      switch (n) {
          case 1: r = "uno";
          case 2: r = "dos";
          case 3: r = "tres"; break;
          default: r = "otro";
      }
      return r;
  }
  ```
- [ ] **A4** ⭐ Reescribe con el operador ternario: `if (a > b) { m = a; } else { m = b; }`

> [!question]- Respuestas de la Parte A
> **A1:** `AMBOS`, `TRES`, `CINCO`, `NINGUNO`.
>
> **A2:** (1) <code>&#61;&#61;</code> con `String` → usar `nombre.equals("Ana")`; (2) el `;` después del `if` hace que el bloque se ejecute siempre; (3) sin llaves, `r = r + "!";` no pertenece al segundo `if` y se ejecuta siempre.
>
> **A3:** `tipo(2)` → `"tres"` (falta `break` después de `case 2`, así que cae en `case 3`). `tipo(5)` → `"otro"`. Faltan los `break` en `case 1` y `case 2`.
>
> **A4:** `m = a > b ? a : b;`

---

## Parte B · Decisiones básicas

- [ ] **B1** ⭐ `signo(int n)` → `"POSITIVO"`, `"NEGATIVO"` o `"CERO"`.
- [ ] **B2** ⭐ `mayor(int a, int b)` y luego `mayor(int a, int b, int c)` reutilizando el primero.
- [ ] **B3** ⭐ `evaluarNota(double nota)` → `"NOTA INVÁLIDA"`, `"APROBADO"` (≥ 51), `"CASO ESPECIAL"` (de 50 a menos de 51) o `"REPROBADO"`.
- [ ] **B4** ⭐ `precioConDescuento(double precio)` → 10 % de descuento si el precio pasa de Bs. 100 (`if` sin `else`).
- [ ] **B5** ⭐⭐ `tipoTriangulo(double a, double b, double c)` → `"NO ES TRIÁNGULO"`, `"EQUILÁTERO"`, `"ISÓSCELES"` o `"ESCALENO"`. (Tres lados forman un triángulo si cada uno es menor que la suma de los otros dos.)
- [ ] **B6** ⭐⭐ `tipoCaracter(char c)` → `"VOCAL"`, `"CONSONANTE"`, `"DÍGITO"` u `"OTRO"` (considera mayúsculas y minúsculas).
- [ ] **B7** ⭐⭐ `tarifaTaxi(double km)`: Bs. 10 la bajada de bandera, que incluye los 2 primeros km; Bs. 3 cada km adicional; con un 20 % de recargo si el viaje pasa de 15 km.
- [ ] **B8** ⭐⭐ `calcularIMC(double peso, double talla)` y `clasificarIMC(double imc)` → bajo peso (< 18.5), normal (< 25), sobrepeso (< 30), obesidad.
- [ ] **B9** ⭐⭐ `ordenarTres(int a, int b, int c)` → un `String` con los tres números ordenados de menor a mayor.
- [ ] **B10** ⭐⭐ `cajero(double saldo, double monto)` → `"Monto inválido"` si `monto <= 0`, `"Saldo insuficiente"` si `monto > saldo`, o `"Retiro exitoso. Nuevo saldo: …"`.

> [!tip]- Pista B9
> El menor es `Math.min(a, Math.min(b, c))`, el mayor es `Math.max(…)` y el del medio es `a + b + c - menor - mayor`.

---

## Parte C · `switch`

- [ ] **C1** ⭐ `nombreMes(int m)` → `"Enero"` … `"Diciembre"` o `"Mes inválido"`.
- [ ] **C2** ⭐⭐ `diasDelMes(int m, int anio)` → 28, 29, 30 o 31 (agrupa los `case` que tienen los mismos días y usa `esBisiesto`).
- [ ] **C3** ⭐⭐ `operar(double a, char op, double b)` → la calculadora de los apuntes, pero que devuelva un `String` y diga `"No se puede dividir entre 0"`.
- [ ] **C4** ⭐⭐ `literal(int nota)` → `"A"` (90–100), `"B"` (80–89), `"C"` (70–79), `"D"` (51–69), `"F"` (0–50). Resuélvelo con `switch (nota / 10)`.

> [!tip]- Pista C4
> `nota / 10` convierte 0–100 en 0–10. Los `case 10:` y `case 9:` dan `"A"`, `case 8:` da `"B"`… ¿Y del 51 al 59?

---

## Parte D · Problemas tipo examen ⭐⭐⭐

- [ ] **D1 · ¡Alcanza el número!** Dos jugadores parten de 0 y, por turnos, suman un incremento de **1 a 4**. Gana quien llega **exactamente** al número objetivo; si alguien lo pasa, es empate. Crea la clase `Juego` con los atributos `objetivo` y `acumulado`:
  1. El constructor elige un objetivo aleatorio en $[10, 60)$ y pone `acumulado` en 0.
  2. `public boolean esIncrementoValido(int inc)`
  3. `public String jugar(int inc)`: si el incremento no es válido, devuelve `"Incremento inválido"`; si no, actualiza `acumulado` y devuelve `"Acumulado: X"`, `"¡GANASTE!"` o `"EMPATE: te pasaste"`.
  4. Extra: `public int jugadaComputadora()` que devuelva el incremento que deja <code>(objetivo - acumulado) % 5 &#61;&#61; 0</code>, o `1` si no es posible.

- [ ] **D2 · ¿Mayor o menor?** La computadora piensa un número secreto entre 1 y 100. En las preguntas **impares** responde `true` si el número dado es **menor o igual** que el secreto; en las **pares**, `true` si es **mayor**. Crea la clase `Adivina` con `numeroSecreto` (aleatorio) y `partida` (contador de preguntas), y el método `public boolean darNumero(int numero)`.

- [ ] **D3 · Cámara frigorífica.** La cámara admite como máximo **100 kg**. Crea la clase `Camara` con el atributo `pesoActual` y el método `public String ingresar(String serie, int vigencia, boolean perecedero, double peso)` que:
  - rechace el producto si `vigencia` no está entre 1 y 10, o si `peso <= 0`;
  - rechace el producto si no cabe;
  - si lo acepta, actualice `pesoActual` y agregue `" (REVISAR PRONTO)"` al mensaje cuando sea perecedero con vigencia menor a 5 años.

- [ ] **D4 · Masitas en cajas.** Una caja tiene `base × altura`. Una masita circular de radio `r` cabe si su diámetro no supera ni la base ni la altura. Crea la clase `Caja` con `base`, `altura`, `masitas` (contador) y `areaOcupada`, y el método `public String ponerMasita(double r)` que devuelva `"Masita ubicada"` (y actualice los atributos) o `"No cabe"`.

- [ ] **D5 · Día siguiente.** `diaSiguiente(int d, int m, int a)` → la fecha del día siguiente como `"d/m/a"` (usa `diasDelMes` de C2).

---

## Autoevaluación

Antes de pasar a la Semana 2, comprueba que puedes:

- [ ] Escribir un `if / else if / else` y elegir datos de prueba para **cada** camino.
- [ ] Escribir condicionales anidados y usar el operador ternario.
- [ ] Usar `switch` con `int`, `char` y `String`, sin olvidar `break` ni `default`.
- [ ] Explicar cuándo conviene `switch` y cuándo `if`.
- [ ] Reconocer los tres errores clásicos con `if`.

> [!quote] Fin de la Semana 1
> Ya sabes calcular, decidir y organizar tu código en métodos. La próxima semana aprenderás a **repetir**: los algoritmos con repetición del [[Día 01 - Apuntes#6. Elementos básicos de un algoritmo|Día 1]] por fin pasan a Java.
