---
tipo: practica
dia: 2
semana: 1
tema: Clases, tipos de datos, variables y constantes en BlueJ
tags: [java, intro-programacion, dia-02, practica]
---

# Práctica · Día 2

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 02 - Apuntes|apuntes del Día 2]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Trabaja en **BlueJ**, en un proyecto llamado `Dia02`.
> - Primero **predice** el resultado en papel y después compruébalo en BlueJ.

---

## Parte A · Estructura de una clase

- [ ] **A1** ⭐ Crea la clase `Ejemplo` en BlueJ **sin modificar la plantilla**. Compílala, crea un objeto, inspecciónalo y ejecuta su método con el parámetro `5`. ¿Qué valor devuelve? ¿Por qué?
- [ ] **A2** ⭐ En la plantilla de la clase `Ejemplo`, señala con comentarios: los atributos, el constructor, los métodos, cada bloque `{ }` y el comentario Javadoc. Pulsa `Ctrl+J` y describe lo que ves.
- [ ] **A3** ⭐ Crea la clase `Auto` con los atributos `marca` (`String`), `color` (`String`), `anio` (`int`) y `precio` (`double`). En el constructor dales valores iniciales. Crea **dos** objetos e inspecciónalos.

## Parte B · Tipos de datos

- [ ] **B1** ⭐ Elige el tipo de dato más adecuado y declara (con un valor de ejemplo) una variable para cada caso:
  1. La edad de una persona
  2. El precio de un producto en bolivianos
  3. Si un estudiante está inscrito o no
  4. La inicial del apellido
  5. El nombre de la carrera
  6. La población del mundo
  7. El código SIS de un estudiante
  8. La nota final de una materia (puede ser 50.5)
- [ ] **B2** ⭐⭐ Crea la clase `TiposDeDatos` con un atributo de **cada** tipo primitivo (`byte`, `short`, `int`, `long`, `float`, `double`, `boolean`, `char`) más un `String`. Compílala e inspecciona un objeto.
- [ ] **B3** ⭐⭐ Encuentra el error de cada línea **sin compilar**, escribe el mensaje que crees que dará el compilador y luego compruébalo en BlueJ:
  ```java
  byte b = 200;
  long l = 9000000000;
  float f = 3.14;
  char c = "A";
  String s = 'Hola';
  int 2numero = 5;
  double class = 1.5;
  boolean v = "true";
  ```
- [ ] **B4** ⭐⭐ ¿Qué guarda cada variable? Predice y luego compruébalo con el inspector:
  ```java
  char c1 = 65;
  char c2 = 'a' + 2;
  int  i1 = 'Z';
  int  i2 = '9' - '0';
  int  i3 = 0x1F;
  int  i4 = 0b1010;
  ```

## Parte C · Variables, alcance y constantes

- [ ] **C1** ⭐ Crea la clase `Circulo` con el atributo `radio` y la constante `final double PI = 3.1416;`. Intenta asignarle otro valor a `PI` dentro de un método. Copia el mensaje de error.
- [ ] **C2** ⭐⭐ Este código no compila. Encuentra **todos** los errores y explica cada uno usando el concepto de **alcance**:
  ```java
  public class Errores {
      private int total;

      public void sumar(int a) {
          int parcial = a * 2;
          total = total + parcial;
      }

      public int obtener() {
          return parcial + a;
      }
  }
  ```
- [ ] **C3** ⭐⭐ Clasifica cada variable como **atributo**, **parámetro** o **local**, e indica dónde **muere**:
  ```java
  public class Tienda {
      private String nombre;
      private int ventas;

      public Tienda() {
          nombre = "Mi tienda";
          ventas = 0;
      }

      public int registrar(int cantidad) {
          int nuevas = cantidad + 1;
          ventas = ventas + nuevas;
          return ventas;
      }
  }
  ```

## Parte D · Del algoritmo a la clase

- [ ] **D1** ⭐⭐ Crea la clase `Estudiante` con los atributos `nombre`, `codigoSis`, `nota1`, `nota2` y la constante `NOTA_MINIMA = 51`. Escribe un constructor que inicialice todo y comprueba con el inspector que los valores son los esperados.
- [ ] **D2** ⭐⭐⭐ **Mini-proyecto.** Modela con una clase uno de estos objetos de la vida real. Decide sus atributos (con el tipo correcto), al menos una constante y su constructor:
  - Un **producto** de una tienda (código, nombre, precio, stock, si es perecedero)
  - Una **cuenta bancaria** (titular, número, saldo, si está activa)
  - Un **personaje** de videojuego (nombre, vida, ataque, nivel, inicial del equipo)

> [!tip]- Pista B3
> Hay 8 líneas y 8 errores: rango de `byte`, falta de sufijo `L`, falta de sufijo `F`, comillas dobles en un `char`, comillas simples en un `String`, nombre que empieza con dígito, palabra reservada como nombre y texto en un `boolean`.

> [!tip]- Pista C2
> `parcial` se declaró dentro de `sumar`: ¿dónde muere? ¿Y `a`?


---

## Autoevaluación

Antes de pasar al [[Día 03 - Apuntes|Día 3]], comprueba que puedes:

- [ ] Crear una clase en BlueJ, compilarla, crear objetos e inspeccionarlos.
- [ ] Señalar atributos, constructor y métodos en una clase Java.
- [ ] Elegir el tipo de dato correcto y explicar por qué `long` lleva `L` y `float` lleva `F`.
- [ ] Explicar la relación entre `char` y los códigos ASCII.
- [ ] Explicar el alcance de una variable y qué hace `final`.
