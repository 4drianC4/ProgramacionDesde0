---
tipo: diapositivas
dia: 4
semana: 1
tags: [java, intro-programacion, dia-04, diapositivas]
theme: white
transition: slide
---

# Día 4

## Métodos y entrada de datos

**Programación desde 0** · Semana 1 · Jueves

---

# Hoy vamos a…

1. Escribir **métodos** con parámetros y `return`
2. Hacer que un método **use a otro**
3. Entender **`static`** y **`main`**
4. Leer datos con **`Scanner`**

Apuntes completos: [[Día 04 - Apuntes]]

---

# Estructura de un método

```java
public int sumar(int a, int b) {
    int suma = a + b;
    return suma;
}
```

**acceso** · **tipo de retorno** · **nombre** · **(parámetros)** · **{ cuerpo }** · **return**

---

# Las partes

| Parte | Ejemplos |
|---|---|
| Acceso | `public` · `private` |
| Retorno | `int` `double` `boolean` `String` · **`void`** |
| Nombre | verbo en camelCase: `calcularPromedio` |
| Parámetros | datos que llegan de afuera |
| `return` | entrega el resultado |

---

# Tres formas comunes

```java
public double promedio(double a, double b) {
    return (a + b) / 2;
}
public boolean esPar(int n) {
    return n % 2 == 0;
}
public void reiniciar() {
    contador = 0;
}
```

---

# Métodos que usan métodos

```java
public double promedioTres(double a, double b, double c) {
    return (a + b + c) / 3;
}
public boolean aprobo(double a, double b, double c) {
    double p = promedioTres(a, b, c);
    return p >= 51;
}
```

Divide un problema grande en partes pequeñas.

---

# static

- **Sin** `static` → del **objeto** → primero `new`
- **Con** `static` → de la **clase** → `Math.sqrt(9)`

> [!warning] Error frecuente
> *non-static method cannot be referenced from a static context* → crea un objeto o usa `static`.

---

# main + Scanner

```java
import java.util.Scanner;

public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int n1 = sc.nextInt();
    int n2 = sc.nextInt();
    Calculadora calc = new Calculadora();
    System.out.println(calc.sumar(n1, n2));
}
```

---

# El patrón del curso

**Usuario escribe → Scanner lee → variables → método de lógica → return → println muestra**

> [!important] Devolver vs. mostrar
> La **lógica devuelve**. Solo `main` **imprime**.

---

# Leer con Scanner

| Método | Lee |
|---|---|
| `nextInt()` | `int` |
| `nextDouble()` | `double` |
| `next()` | una palabra |
| `nextLine()` | una línea |
| `next().charAt(0)` | un `char` |

---

# Dos trampas de Scanner

1. `nextDouble()` y la **coma decimal** →
   `sc.useLocale(java.util.Locale.US);`
2. `nextLine()` después de `nextInt()` lee **vacío** →
   agrega un `sc.nextLine();` extra

---

# Mostrar resultados

| Instrucción | Hace |
|---|---|
| `println(x)` | muestra y **salta** de línea |
| `print(x)` | muestra **sin** saltar |
| `printf("%.2f%n", x)` | muestra con **2 decimales** |

---

# Del pseudocódigo a Java

| Día 1 | Java |
|---|---|
| `Leer X` | `x = sc.nextInt();` |
| `Mostrar S` | `System.out.println(s);` |
| un subproblema | un **método** que devuelve |

---

# Resumen

- Método = acceso + retorno + nombre + parámetros + `return`
- `void` no devuelve nada
- `static` es de la clase · `main` crea objetos
- **Scanner** lee · la lógica **devuelve** · `main` **muestra**

---

# Tu turno

✍️ [[Día 04 - Práctica]]

➡️ Mañana: **decisiones con `if` y `switch`**
