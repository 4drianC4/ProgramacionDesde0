---
tipo: diapositivas
dia: 8
semana: 2
tags: [java, intro-programacion, dia-08, diapositivas]
theme: white
transition: slide
---

# Día 8

## Cadenas: String y char

**Programación desde 0** · Semana 2 · Miércoles

---

# Hoy vamos a…

1. Usar los **métodos** de `String`
2. **Recorrer** una cadena
3. Clasificar caracteres con **`Character`**
4. **Construir** cadenas nuevas
5. Convertir **texto ↔ número**

Apuntes completos: [[Día 08 - Apuntes]]

---

# ¿Qué es un String?

- Una **secuencia de `char`**: `"Hola"`
- Es una **clase**: tiene métodos → `s.length()`
- Es **inmutable**: sus métodos devuelven una cadena **nueva**

```java
s.toUpperCase();      // no cambia s
s = s.toUpperCase();  // ahora sí
```

---

# Índices

| 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| J | A | V | A | ␣ | 8 |

- `length()` = **6**
- Último índice = `length() - 1` = **5**

> [!danger] Fuera de rango
> `charAt(6)` → `StringIndexOutOfBoundsException`

---

# Métodos esenciales

| Método | Ejemplo con `"Programa"` |
|---|---|
| `length()` | `8` |
| `charAt(i)` | `charAt(0)` → `'P'` |
| `indexOf(x)` | `indexOf('g')` → `3` |
| `substring(a, b)` | `substring(0, 3)` → `"Pro"` |
| `toUpperCase()` | `"PROGRAMA"` |

---

# Más métodos

| Método | Pregunta / hace |
|---|---|
| `equals(t)` | ¿mismo texto? |
| `equalsIgnoreCase(t)` | sin importar mayúsculas |
| `contains(t)` | ¿contiene? |
| `replace(a, b)` | reemplaza |
| `trim()` | quita espacios de los bordes |
| `compareTo(t)` | orden alfabético |

---

# substring(a, b)

Desde `a` hasta **`b - 1`**

```java
"Programacion".substring(3, 7)   // "gram"
"Programacion".substring(8)      // "cion"
```

Devuelve `b - a` caracteres.

---

# Recorrer una cadena

```java
for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);
    // hacer algo con c
}
```

**El patrón más importante del día.**

---

# Contar vocales

```java
int cont = 0;
String t = s.toLowerCase();
for (int i = 0; i < t.length(); i++) {
    char c = t.charAt(i);
    if ("aeiou".indexOf(c) >= 0) {
        cont++;
    }
}
```

---

# La clase Character

| Método | Pregunta |
|---|---|
| `isLetter(c)` | ¿letra? |
| `isDigit(c)` | ¿dígito? |
| `isUpperCase(c)` | ¿mayúscula? |
| `isWhitespace(c)` | ¿espacio? |
| `toUpperCase(c)` | convierte |

`c - '0'` → valor del dígito · `c - 'a'` → posición de la letra

---

# Construir cadenas

```java
String r = "";
for (int i = s.length() - 1; i >= 0; i--) {
    r += s.charAt(i);
}
// r es s al revés
```

Palíndromo: `t.equals(invertir(t))`

---

# Cifrado César

```java
char c = texto.charAt(i);
if (c >= 'a' && c <= 'z') {
    int pos = (c - 'a' + n) % 26;
    r += (char) ('a' + pos);
} else {
    r += c;
}
```

---

# Comparar

| Para… | Usa |
|---|---|
| mismo texto | `a.equals(b)` |
| sin mayúsculas | `a.equalsIgnoreCase(b)` |
| orden alfabético | `a.compareTo(b) < 0` |

> [!danger] Nunca `a == b` con `String`

---

# Texto ↔ número

| De → a | Código |
|---|---|
| `"42"` → `42` | `Integer.parseInt(s)` |
| `"3.5"` → `3.5` | `Double.parseDouble(s)` |
| `42` → `"42"` | `String.valueOf(n)` |

---

# Leer texto

```java
String frase = sc.nextLine();   // toda la línea
String palabra = sc.next();     // hasta el espacio
```

---

# Resumen

- Índices de `0` a `length() - 1`
- `charAt` · `substring` · `indexOf` · `equals` · `replace`
- Recorrer: `for` + `charAt(i)`
- Inmutable: construye una cadena **nueva**
- `parseInt` · `parseDouble` · `valueOf`

---

# Tu turno

✍️ [[Día 08 - Práctica]]

➡️ Mañana: **arreglos**
