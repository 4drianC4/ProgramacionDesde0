---
tipo: diapositivas
dia: 5
semana: 1
tags: [java, intro-programacion, dia-05, diapositivas]
theme: white
transition: slide
---

# Día 5

## Decisiones

**Programación desde 0** · Semana 1 · Viernes

---

# Hoy vamos a…

1. Tomar decisiones con **`if`** y **`else`**
2. Varios caminos con **`else if`**
3. Anidar y usar el **ternario**
4. Elegir valores con **`switch`**
5. **Probar** cada camino

Apuntes completos: [[Día 05 - Apuntes]]

---

# if: tomar decisiones

```java
if (precio > 100) {
    res = precio * 0.9;
}
```

Se ejecuta **solo si** la condición es `true`.

La condición es **una pregunta**: una expresión `boolean`.

---

# if - else

```java
if (nota >= 51) {
    res = "APROBADO";
} else {
    res = "REPROBADO";
}
```

Uno de los dos **siempre** se ejecuta, **nunca** ambos.
El `else` no lleva condición.

---

# else if

```java
if (nota < 0 || nota > 100) {
    res = "NOTA INVÁLIDA";
} else if (nota >= 51) {
    res = "APROBADO";
} else if (nota >= 50) {
    res = "CASO ESPECIAL";
} else {
    res = "REPROBADO";
}
```

Se ejecuta la **primera** condición verdadera.

---

# Anidados y ternario

```java
if (monto > 0) {
    if (monto <= saldo) { res = "Retiro exitoso"; }
    else { res = "Saldo insuficiente"; }
}
```

```java
int mayor = a > b ? a : b;
```

---

# switch

```java
switch (dia) {
    case 1: nombre = "Lunes"; break;
    case 2: nombre = "Martes"; break;
    case 6:
    case 7: nombre = "Fin de semana"; break;
    default: nombre = "Día inválido";
}
```

---

# switch: las partes

| Parte | Qué hace |
|---|---|
| `switch (x)` | variable a comparar: `int`, `char`, `String` |
| `case v:` | empieza aquí si <code>x &#61;&#61; v</code> |
| `break;` | sale del `switch` |
| `default:` | si ningún `case` coincide |

> [!warning] Sin `break`
> La ejecución **cae** al siguiente `case`.

---

# ¿switch o if?

- Valores **exactos** de una variable → `switch`
- **Rangos** o condiciones compuestas → `if / else if`

`nota >= 51` no se puede con `switch`.

---

# Tres errores clásicos

```java
if (nota >= 51);          // el ; termina el if
if (nota >= 51)
    res = "APROBADO";
    contador++;           // NO es parte del if
if (nombre == "Ana")      // usa .equals()
```

**Siempre usa llaves.**

---

# Probar un if

**Un dato por cada camino + los límites**

| nota | Resultado |
|---|---|
| 75 | APROBADO |
| 51 | APROBADO (límite) |
| 50.5 | CASO ESPECIAL |
| 30 | REPROBADO |
| 120 | NOTA INVÁLIDA |

---

# Resumen

- `if` / `else if` / `else`: la **primera** verdadera
- Ternario: `c ? a : b`
- `switch` + `break` + `default`
- Siempre con **llaves**
- Un dato de prueba por **camino**

---

# Tu turno

✍️ [[Día 05 - Práctica]]

➡️ El lunes: **ciclos `while` y `do-while`**
