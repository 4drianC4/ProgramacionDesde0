---
tipo: diapositivas
dia: 6
semana: 2
tags: [java, intro-programacion, dia-06, diapositivas]
theme: white
transition: slide
---

# Día 6

## Ciclos while y do-while

**Programación desde 0** · Semana 2 · Lunes

---

# Hoy vamos a…

1. **Repetir** con `while` y `do-while`
2. Reconocer las **tres partes** de un ciclo
3. Usar **contadores, acumuladores, centinelas y banderas**
4. Recorrer los **dígitos** de un número

Apuntes completos: [[Día 06 - Apuntes]]

---

# ¿Por qué repetir?

```text
3. C ← C + 1
4. S ← S + C
5. Si C < 10 Entonces Ir a 3
```

En Java no hay "Ir a". Para repetir usamos **ciclos**.

---

# while

```java
while (condición) {
    // se repite MIENTRAS la condición sea true
}
```

La condición se revisa **antes** de cada vuelta.
Si empieza en `false`, el cuerpo **no se ejecuta**.

---

# Suma del 1 al 10

```java
int c = 0;
int s = 0;
while (c < 10) {
    c = c + 1;
    s = s + c;
}
// s = 55
```

¡Es el mismo algoritmo del Día 1!

---

# Las tres partes

| Parte | Ejemplo |
|---|---|
| **Inicialización** | `int c = 0;` |
| **Condición** | `c < 10` |
| **Actualización** | `c = c + 1;` |

> [!danger] Sin actualización
> La condición nunca cambia → **ciclo infinito**.

---

# Prueba de escritorio

`f = 1; i = 1; while (i <= 5) { f *= i; i++; }`

| i | ¿i ≤ 5? | f |
|---|---|---|
| 1 | sí | 1 |
| 2 | sí | 2 |
| 3 | sí | 6 |
| 4 | sí | 24 |
| 5 | sí | 120 |
| 6 | **no** | sale |

---

# Patrones dentro del ciclo

| Patrón | Antes | Dentro |
|---|---|---|
| Contador | `cont = 0` | `cont++` |
| Suma | `suma = 0` | `suma += x` |
| Producto | `prod = 1` | `prod *= x` |
| Mayor | `mayor = primero` | `if (x > mayor) mayor = x` |

---

# Centinela

Un valor especial que dice **"terminé"**.

```java
int x = sc.nextInt();
while (x != 0) {
    suma += x;
    x = sc.nextInt();   // leer el siguiente
}
```

Se lee **antes** del ciclo y **al final** del cuerpo.

---

# Bandera

Un `boolean` que **recuerda** si algo pasó.

```java
boolean primo = n > 1;
int d = 2;
while (d * d <= n && primo) {
    if (n % d == 0) { primo = false; }
    d++;
}
```

---

# do-while

```java
do {
    // se ejecuta AL MENOS una vez
} while (condición);
```

Primero **hace**, después **pregunta**.
¡Lleva `;` al final!

---

# while vs do-while

| | `while` | `do-while` |
|---|---|---|
| Revisa | antes | después |
| Mínimo | 0 vueltas | **1 vuelta** |
| Uso | repetir mientras… | **validar** y **menús** |

---

# Validar una entrada

```java
int nota;
do {
    System.out.print("Nota (0-100): ");
    nota = sc.nextInt();
} while (nota < 0 || nota > 100);
```

Se repite **mientras** el dato sea inválido.

---

# Recorrer dígitos

```java
int suma = 0;
while (n > 0) {
    suma += n % 10;   // último dígito
    n = n / 10;       // quitarlo
}
```

Funciona con **cualquier** cantidad de cifras.

---

# Invertir un número

```java
int inv = 0;
while (n > 0) {
    inv = inv * 10 + n % 10;
    n = n / 10;
}
```

| n | inv |
|---|---|
| 123 | 0 |
| 12 | 3 |
| 1 | 32 |
| 0 | **321** |

---

# Errores comunes

```java
while (i < 10);        // ";" → ciclo vacío
int suma;              // sin inicializar
while (…) {
    int suma = 0;      // se reinicia cada vuelta
}
} while (x > 0)        // falta ";"
```

---

# Resumen

- `while`: 0 o más vueltas · `do-while`: 1 o más
- Inicialización · condición · actualización
- Contador · acumulador · centinela · bandera
- Dígitos: `% 10` y `/ 10` mientras `n > 0`

---

# Tu turno

✍️ [[Día 06 - Práctica]]

➡️ Mañana: **ciclo `for` y ciclos anidados**
