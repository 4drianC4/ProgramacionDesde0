---
tipo: practica
dia: 4
semana: 1
tema: Métodos, static, main y Scanner
tags: [java, intro-programacion, dia-04, practica]
---

# Práctica · Día 4

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 04 - Apuntes|apuntes del Día 4]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Proyecto de BlueJ: `Dia04`.
> - **Regla del curso:** la lógica va en métodos que **devuelven** su resultado (`return`). Solo `main` lee con `Scanner` e imprime.

---

## Parte A · Leer métodos (en papel)

- [ ] **A1** ⭐ Para cada método indica su **modificador de acceso**, **tipo de retorno**, **nombre** y **parámetros**:
  ```java
  public double areaCirculo(double r) { … }
  private boolean esVocal(char c) { … }
  public void reiniciar() { … }
  public String saludar(String nombre, int hora) { … }
  ```
- [ ] **A2** ⭐ Encuentra el error de cada método:
  ```java
  public int doble(int n) {
      int r = n * 2;
  }

  public void mostrar(int n) {
      return n;
  }

  public double mitad(int n) {
      return n / 2;
  }
  ```
- [ ] **A3** ⭐⭐ ¿Qué devuelve `calcular(3, 4)`?
  ```java
  public int cuadrado(int x) {
      return x * x;
  }
  public int calcular(int a, int b) {
      return cuadrado(a) + cuadrado(b) - cuadrado(a - b);
  }
  ```
- [ ] **A4** ⭐⭐ Este `main` no compila. ¿Por qué? Da **dos** formas de arreglarlo.
  ```java
  public class Area {
      public double rectangulo(double b, double h) {
          return b * h;
      }
      public static void main(String[] args) {
          System.out.println(rectangulo(3, 4));
      }
  }
  ```

> [!question]- Respuestas de la Parte A
> **A2:** (1) falta el `return r;` · (2) un método `void` no puede devolver un valor · (3) compila, pero `n / 2` es división **entera**: `mitad(5)` devuelve `2.0`. Debe ser `n / 2.0`.
>
> **A3:** `9 + 16 - 1 = 24`.
>
> **A4:** `main` es `static` y `rectangulo` no. Arreglos: crear un objeto (`Area a = new Area(); a.rectangulo(3, 4)`) o declarar `rectangulo` como `static`.

---

## Parte B · Escribir métodos

Crea la clase `Calculos` y prueba cada método con clic derecho sobre un objeto.

- [ ] **B1** ⭐ `public double areaTriangulo(double base, double altura)`
- [ ] **B2** ⭐ `public double perimetroCirculo(double r)`
- [ ] **B3** ⭐⭐ `public String convertirSegundos(int seg)` → `"1 h 2 min 5 s"` para 3725.
- [ ] **B4** ⭐⭐ `public double precioFinal(double precio, int cantidad)` que reutilice un método `private double subtotal(double precio, int cantidad)` y sume un 13 % de IVA.
- [ ] **B5** ⭐⭐ `public double distancia(double x1, double y1, double x2, double y2)` y luego `public double perimetroTriangulo(…)` con los 3 vértices, **reutilizando** `distancia`.
- [ ] **B6** ⭐⭐ `public double promedioPonderado(double p1, double p2, double examen)` donde los parciales valen 30 % cada uno y el examen 40 %.
- [ ] **B7** ⭐⭐ Clase `Cuenta` con el atributo `saldo` y los métodos `void depositar(double monto)`, `void retirar(double monto)` y `double getSaldo()`. Pruébala creando un objeto e inspeccionándolo después de cada operación.

> [!tip]- Pista B3
> `seg / 3600` son las horas. `seg % 3600` es lo que sobra; de ahí sacas los minutos con `/ 60` y los segundos con `% 60`.

> [!tip]- Pista B4
> Un método `private` no aparece en el menú del objeto de BlueJ, pero sí lo puede usar otro método de la **misma** clase.

---

## Parte C · Entrada de datos con `Scanner`

- [ ] **C1** ⭐ Agrega un `main` a `Calculos` que lea la base y la altura, llame a `areaTriangulo` y muestre: `El área es: 6.0`.
- [ ] **C2** ⭐ Programa que lea el nombre (`nextLine`) y la edad (`nextInt`) y muestre: `Hola Ana, el próximo año tendrás 21 años.`
- [ ] **C3** ⭐⭐ Programa que lea un `double`. Pruébalo escribiendo `4.5` y luego `4,5`. ¿Qué pasa? Arréglalo con `useLocale`.
- [ ] **C4** ⭐⭐ Programa que lea **primero** la edad (`nextInt`) y **luego** el nombre (`nextLine`). ¿Qué falla? Arréglalo.
- [ ] **C5** ⭐⭐ Programa que lea un `char` (con `next().charAt(0)`) y muestre su código ASCII y la letra siguiente.
- [ ] **C6** ⭐⭐ Programa que lea un precio y una cantidad y muestre el total con **2 decimales** usando `printf` y el método `precioFinal` de B4.

---

## Parte D · Mini-proyecto ⭐⭐⭐

- [ ] **D1 · Boleta de compra.** Crea la clase `Boleta` con estos métodos (todos devuelven su resultado):
  - `double subtotal(double precio, int cantidad)`
  - `double descuento(double subtotal, double porcentaje)`
  - `double iva(double monto)` → 13 %
  - `double total(double precio, int cantidad, double porcentaje)` → reutiliza los tres anteriores

  Escribe un `main` que lea el nombre del producto, el precio, la cantidad y el porcentaje de descuento, y muestre:
  ```text
  Producto:  Cuaderno
  Subtotal:  Bs. 60.00
  Descuento: Bs.  6.00
  IVA:       Bs.  7.02
  TOTAL:     Bs. 61.02
  ```

---

## Autoevaluación

Antes de pasar al [[Día 05 - Apuntes|Día 5]], comprueba que puedes:

- [ ] Escribir un método con parámetros y `return`, y explicar qué significa `void`.
- [ ] Hacer que un método use a otro método de la misma clase.
- [ ] Explicar por qué `main` no puede llamar directamente a un método sin `static`.
- [ ] Leer `int`, `double`, `String` y `char` con `Scanner`.
- [ ] Mostrar resultados con `println` y con `printf` usando 2 decimales.
