---
tipo: diapositivas
dia: 1
semana: 1
tags: [java, intro-programacion, dia-01, diapositivas]
theme: white
transition: slide
---

# Día 1

## La computadora y los algoritmos

**Programación desde 0** · Semana 1 · Lunes

---

# Hoy vamos a…

1. Entender qué hace una computadora y por qué usa **binario**
2. Ver cómo se ejecuta un programa en **Java**
3. Escribir **algoritmos**
4. Comprobarlos con la **prueba de escritorio**

Apuntes completos: [[Día 01 - Apuntes]]

---

# ¿Qué hace una computadora?

**Entrada → Proceso → Salida**, y guarda datos en **memoria**.

| | Ejemplo |
|---|---|
| Entrada | Teclado, archivo |
| Proceso | CPU |
| Salida | Pantalla, archivo |
| Memoria | RAM: tus variables |

---

# Hardware y software

- **Hardware:** lo que se toca → CPU, RAM, disco, teclado
- **Software:** las instrucciones → sistema operativo, BlueJ, **tus programas**

Programar = escribir software que le dice al hardware qué hacer.

---

# ¿Por qué binario?

Un circuito solo distingue **dos estados**: hay corriente / no hay corriente → **1 / 0**

- 1 **bit** = un 0 o un 1
- 1 **byte** = 8 bits = 256 valores
- Con *n* bits: **2ⁿ** valores

`26` en decimal = `11010` en binario → 16 + 8 + 2

---

# Lenguajes de programación

| Nivel | Cómo se ve |
|---|---|
| Máquina | `10110000 01100001` |
| Ensamblador | `MOV AL, 61h` |
| **Alto nivel** | `int edad = 20;` |

Java es de **alto nivel**: hay que **traducirlo**.

---

# De tu código a la ejecución

**`Ejemplo.java`** → *compilar* → **`Ejemplo.class`** (bytecode) → **JVM** → cualquier sistema operativo

> [!important] Compilar
> Revisa que esté **bien escrito**. Que compile **no** significa que funcione bien: puede tener **errores de lógica**.

---

# ¿Qué es un algoritmo?

Una secuencia **finita** y **ordenada** de pasos que resuelve un problema.

Como una **receta de cocina**: pasos numerados, en orden, que terminan.

**Características:** finito · correcto · robusto · completo · eficiente

---

# Pasos para resolver un problema

1. **Análisis:** ¿qué tengo? ¿qué debo obtener?
2. **Diseño:** el algoritmo
3. **Prueba de escritorio:** simularlo a mano
4. **Codificación:** pasarlo a Java
5. **Prueba:** ejecutarlo con varios datos

---

# La memoria: un casillero

| Variable | Contenido |
|---|---|
| `S` | 100 |
| `C` | −1 |
| `SUMA` | *basura* |

> [!warning] La memoria no empieza limpia
> Siempre da un **valor inicial** antes de usar una variable.

---

# Elementos básicos

| Elemento | Pseudocódigo |
|---|---|
| Asignación | `Z ← Z + 3` |
| Contador | `C ← 0` … `C ← C + 1` |
| Acumulador | `S ← 0` … `S ← S + X` |
| Leer / Mostrar | `Leer X` · `Mostrar S` |
| Condicional | `Si A > B Entonces … Sino …` |
| Repetición | `Si C < 10 Entonces Ir a 3` |

---

# Ejemplo: sumar del 1 al 10

```text
1. C ← 0
2. S ← 0
3. C ← C + 1
4. S ← S + C
5. Si C < 10 Entonces Ir a 3
6. Mostrar "La suma es: ", S
7. FIN
```

`C` cuenta · `S` acumula · pasos 1–2 **una sola vez**

---

# Prueba de escritorio

Una columna por variable, un valor nuevo por paso:

| C | S | ¿C < 10? |
|---|---|---|
| 0 | 0 | |
| 1 | 1 | sí |
| 2 | 3 | sí |
| … | … | … |
| 10 | 55 | **no** → mostrar |

---

# ¿Con qué datos probar?

1. Datos **fáciles** → ¿funciona?
2. Datos que lo hagan **fallar** → cero, negativos, límites
3. **Un dato por cada caso** posible

Nota: ≥ 51 APROBADO · < 50 REPROBADO · 50–51 ESPECIAL → probar **70, 40 y 50.5**

---

# Resumen

- Entrada → proceso → salida, en **binario**
- Java → **bytecode** → **JVM**
- Algoritmo: finito y ordenado
- **Prueba de escritorio**: los valores paso a paso

---

# Tu turno

✍️ [[Día 01 - Práctica]]

➡️ Mañana: **tu primera clase en Java**
