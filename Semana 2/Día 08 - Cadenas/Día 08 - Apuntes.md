---
tipo: apuntes
dia: 8
semana: 2
tema: "Cadenas: String y char"
tags: [java, intro-programacion, dia-08, apuntes]
---

# Día 8 · Cadenas: `String` y `char`

> [!info] Datos de la clase
> **Semana 2 · Miércoles** · **IDE:** BlueJ · **Requisito:** [[Día 07 - Apuntes|Día 7]]
> **Material del día:** [[Día 08 - Diapositivas|Diapositivas]] · [[Día 08 - Práctica|Práctica]] · [[README|Ruta de aprendizaje]]

> [!abstract] Al terminar este día podrás…
> - Usar los métodos principales de **`String`**: `length`, `charAt`, `substring`, `indexOf`, `equals`…
> - **Recorrer** una cadena carácter por carácter con un ciclo.
> - Clasificar caracteres con la clase **`Character`**.
> - **Construir** cadenas nuevas: invertir, reemplazar, cifrar.
> - Convertir entre **texto y números**.

---

### 1. Repaso: ¿qué es un `String`?

- Una **secuencia de caracteres** (`char`) entre comillas dobles: `"Hola"`.
- No es un tipo primitivo: es una **clase** ([[Día 02 - Apuntes#5. Tipos de datos|Día 2]]). Por eso tiene **métodos** que se llaman con un punto: `nombre.length()`.
- Es **inmutable**: sus métodos no cambian el texto original, sino que **devuelven uno nuevo**.

```java
String s = "hola";
s.toUpperCase();          // ✘ no cambia s
s = s.toUpperCase();      // ✔ ahora s es "HOLA"
```

### 2. Índices: las posiciones de una cadena

Cada carácter tiene una **posición** que empieza en **0**.

| Índice | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| `"JAVA 8"` | `J` | `A` | `V` | `A` | ` ` | `8` |

- La cadena tiene `length()` = **6** caracteres.
- El **último** índice es `length() - 1` = **5**.

> [!danger] Fuera de rango
> `s.charAt(6)` con una cadena de 6 caracteres produce el error **`StringIndexOutOfBoundsException`**. Los índices válidos van de `0` a `length() - 1`.

### 3. Métodos esenciales de `String`

Con `String s = "Programacion Java";`

| Método | Devuelve | Ejemplo | Resultado |
|---|---|---|---|
| `length()` | cantidad de caracteres | `s.length()` | `17` |
| `charAt(i)` | el `char` en la posición `i` | `s.charAt(0)` | `'P'` |
| `indexOf(x)` | primera posición de `x` (o `-1`) | `s.indexOf('a')` | `5` |
| `lastIndexOf(x)` | última posición de `x` | `s.lastIndexOf('a')` | `16` |
| `substring(a, b)` | de la posición `a` hasta `b - 1` | `s.substring(0, 4)` | `"Prog"` |
| `substring(a)` | desde `a` hasta el final | `s.substring(13)` | `"Java"` |
| `toUpperCase()` / `toLowerCase()` | en mayúsculas / minúsculas | `s.toUpperCase()` | `"PROGRAMACION JAVA"` |
| `trim()` | sin espacios al inicio y al final | `"  hola ".trim()` | `"hola"` |
| `equals(t)` | ¿mismo texto? | `s.equals("java")` | `false` |
| `equalsIgnoreCase(t)` | ¿mismo texto sin importar mayúsculas? | `"JAVA".equalsIgnoreCase("java")` | `true` |
| `contains(t)` | ¿contiene `t`? | `s.contains("Java")` | `true` |
| `startsWith(t)` / `endsWith(t)` | ¿empieza / termina con `t`? | `s.endsWith("Java")` | `true` |
| `replace(a, b)` | reemplaza todas las `a` por `b` | `"casa".replace('a', 'o')` | `"coso"` |
| `isEmpty()` | ¿tiene 0 caracteres? | `"".isEmpty()` | `true` |
| `compareTo(t)` | orden alfabético: `< 0`, `0` o `> 0` | `"ana".compareTo("beto")` | negativo |

> [!tip] `substring(a, b)` no incluye la posición `b`
> La cantidad de caracteres que devuelve es `b - a`. `"Programacion".substring(3, 7)` → `"gram"` (posiciones 3, 4, 5 y 6).

### 4. Recorrer una cadena

El patrón más importante del día: un `for` de `0` a `length() - 1` con `charAt(i)`.

```java
public int contarVocales(String s) {
    int cont = 0;
    String t = s.toLowerCase();
    for (int i = 0; i < t.length(); i++) {
        char c = t.charAt(i);
        if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
            cont++;
        }
    }
    return cont;
}
```

> [!tip] Otra forma de preguntar "¿es vocal?"
> `"aeiou".indexOf(c) >= 0` es `true` si `c` está en la cadena `"aeiou"`.

### 5. La clase `Character`

Métodos estáticos para preguntar por un `char`:

| Método | Pregunta / devuelve |
|---|---|
| `Character.isLetter(c)` | ¿es una letra? |
| `Character.isDigit(c)` | ¿es un dígito? |
| `Character.isLetterOrDigit(c)` | ¿letra o dígito? |
| `Character.isUpperCase(c)` / `isLowerCase(c)` | ¿mayúscula? / ¿minúscula? |
| `Character.isWhitespace(c)` | ¿espacio, tabulación o salto de línea? |
| `Character.toUpperCase(c)` / `toLowerCase(c)` | la letra convertida |

Y recuerda que un `char` es un número ([[Día 02 - Apuntes#5. Tipos de datos|Día 2]]):

```java
int valor = c - '0';           // '7' → 7
int posicion = c - 'a';        // 'c' → 2
char letra = (char) ('a' + 3); // 'd'
```

### 6. Construir cadenas nuevas

Como un `String` no cambia, se **construye uno nuevo** concatenando en un ciclo:

```java
public String invertir(String s) {
    String r = "";
    for (int i = s.length() - 1; i >= 0; i--) {
        r += s.charAt(i);
    }
    return r;
}

public boolean esPalindromo(String s) {
    String t = s.toLowerCase().replace(" ", "");
    return t.equals(invertir(t));
}
```

> [!note] `StringBuilder`
> Concatenar con `+=` dentro de un ciclo muy largo es lento, porque crea una cadena nueva en cada vuelta. Java tiene la clase `StringBuilder` para eso (`sb.append(c)`, `sb.reverse()`, `sb.toString()`). Para los ejercicios del curso, `+=` es suficiente.

### 7. Algoritmos típicos con cadenas

> [!example] Contar palabras (separadas por un espacio)
> ```java
> public int contarPalabras(String s) {
>     String t = s.trim();
>     if (t.isEmpty()) {
>         return 0;
>     }
>     int cont = 1;
>     for (int i = 0; i < t.length(); i++) {
>         if (t.charAt(i) == ' ') {
>             cont++;
>         }
>     }
>     return cont;
> }
> ```

> [!example] Cifrado César de un texto
> ```java
> public String cifrar(String texto, int n) {
>     String r = "";
>     for (int i = 0; i < texto.length(); i++) {
>         char c = texto.charAt(i);
>         if (c >= 'a' && c <= 'z') {
>             int pos = (c - 'a' + n) % 26;
>             r += (char) ('a' + pos);
>         } else {
>             r += c;               // espacios y otros símbolos quedan igual
>         }
>     }
>     return r;
> }
> ```
> Para **descifrar**, cifra con `26 - n`.

> [!example] Primera letra de cada palabra en mayúscula
> ```java
> public String capitalizar(String s) {
>     String r = "";
>     boolean inicio = true;                 // bandera
>     for (int i = 0; i < s.length(); i++) {
>         char c = s.charAt(i);
>         r += inicio ? Character.toUpperCase(c) : c;
>         inicio = (c == ' ');
>     }
>     return r;
> }
> ```

### 8. Comparar cadenas

| Para… | Usa |
|---|---|
| ¿Mismo texto? | `a.equals(b)` |
| ¿Mismo texto, sin importar mayúsculas? | `a.equalsIgnoreCase(b)` |
| ¿Cuál va primero en orden alfabético? | `a.compareTo(b) < 0` → `a` va antes |

> [!danger] Nunca `==` con `String`
> `==` compara si son el **mismo objeto**, no si tienen el mismo texto ([[Día 03 - Apuntes#5. Operadores relacionales|Día 3]]).

### 9. Convertir entre texto y números

| Conversión | Código | Ejemplo |
|---|---|---|
| `String` → `int` | `Integer.parseInt(s)` | `"42"` → `42` |
| `String` → `double` | `Double.parseDouble(s)` | `"3.5"` → `3.5` |
| número → `String` | `String.valueOf(n)` o `"" + n` | `42` → `"42"` |
| `char` → `String` | `String.valueOf(c)` o `"" + c` | `'a'` → `"a"` |

> [!tip] Contar los dígitos, otra vez
> `String.valueOf(n).length()` da la cantidad de dígitos de un número positivo, sin ciclos.

### 10. Leer texto con `Scanner`

```java
Scanner sc = new Scanner(System.in);
System.out.print("Escribe una frase: ");
String frase = sc.nextLine();    // toda la línea, con espacios
System.out.print("Escribe una palabra: ");
String palabra = sc.next();      // solo hasta el primer espacio
```

---

## Resumen

> [!summary] Lo esencial del Día 8
> - Un `String` es una secuencia de `char` con índices de `0` a `length() - 1`.
> - Métodos clave: `length`, `charAt`, `indexOf`, `substring(a, b)`, `toUpperCase`, `equals`, `replace`.
> - Los métodos de `String` **devuelven** una cadena nueva: el original no cambia.
> - Recorrer: `for (int i = 0; i < s.length(); i++) { char c = s.charAt(i); … }`.
> - `Character.isLetter`, `isDigit`, `toUpperCase`… y `c - 'a'` para la posición de una letra.
> - Texto ↔ número: `Integer.parseInt`, `Double.parseDouble`, `String.valueOf`.

## Siguiente paso

- ✍️ Practica: [[Día 08 - Práctica]]
- 📖 Glosario: [[Glosario]]
- ⬅️ Ayer: [[Día 07 - Apuntes|Día 7 · Ciclo for y ciclos anidados]]
- ➡️ Mañana: [[Día 09 - Apuntes|Día 9 · Arreglos]]
