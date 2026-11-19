---
tipo: practica
dia: 8
semana: 2
tema: Métodos de String, recorrido de cadenas y Character
tags: [java, intro-programacion, dia-08, practica]
---

# Práctica · Día 8

> [!info] Cómo usar esta práctica
> - Antes de empezar, repasa los [[Día 08 - Apuntes|apuntes del Día 8]].
> - Dificultad: ⭐ básico · ⭐⭐ intermedio · ⭐⭐⭐ reto.
> - Proyecto de BlueJ: `Dia08`. Crea la clase `Texto` y agrega un método por ejercicio.

---

## Parte A · Métodos de `String` (en papel)

- [ ] **A1** ⭐ Con `String s = "Universidad Mayor";`, ¿qué devuelve cada expresión?
  1. `s.length()`
  2. `s.charAt(4)`
  3. `s.indexOf('d')`
  4. `s.indexOf("Mayor")`
  5. `s.substring(0, 3)`
  6. `s.substring(12)`
  7. `s.toUpperCase().charAt(1)`
  8. `s.indexOf('z')`
  9. `s.charAt(s.length() - 1)`
  10. `s.replace('a', '4')`
- [ ] **A2** ⭐⭐ ¿Qué imprime?
  ```java
  String a = "Hola";
  a.concat(" mundo");
  System.out.println(a);
  a = a + " mundo";
  System.out.println(a.length());
  System.out.println("abc".compareTo("abd") < 0);
  System.out.println('7' - '0' + 1);
  System.out.println("" + '7' + 1);
  ```
- [ ] **A3** ⭐⭐ ¿Qué devuelve `misterio("programa")`?
  ```java
  public String misterio(String s) {
      String r = "";
      for (int i = 0; i < s.length(); i += 2) {
          r += s.charAt(i);
      }
      return r;
  }
  ```

> [!question]- Respuestas de la Parte A
> **A1:** 1) `17` · 2) `'e'` · 3) `8` · 4) `12` · 5) `"Uni"` · 6) `"Mayor"` · 7) `'N'` · 8) `-1` · 9) `'r'` · 10) `"Universid4d M4yor"`
>
> **A2:** `Hola` (el `String` no cambia) · `10` · `true` · `8` · `71`
>
> **A3:** `"porm"`: los caracteres de las posiciones pares.

---

## Parte B · Recorrer cadenas

- [ ] **B1** ⭐ `int contarVocales(String s)`
- [ ] **B2** ⭐ `int contarLetra(String s, char c)` → cuántas veces aparece `c`.
- [ ] **B3** ⭐ `String invertir(String s)`
- [ ] **B4** ⭐ `boolean esPalindromo(String s)` → ignora mayúsculas y espacios (`"Anita lava la tina"` → `true`).
- [ ] **B5** ⭐⭐ `int contarPalabras(String s)`
- [ ] **B6** ⭐⭐ `String resumen(String s)` → `"Letras: 10, dígitos: 3, espacios: 2, otros: 1"`.
- [ ] **B7** ⭐⭐ `String quitarVocales(String s)`
- [ ] **B8** ⭐⭐ `String capitalizar(String s)` → `"hola mundo"` → `"Hola Mundo"`.
- [ ] **B9** ⭐⭐ `String iniciales(String nombreCompleto)` → `"Juan Pérez Rojas"` → `"JPR"`.
- [ ] **B10** ⭐⭐ `boolean esNumero(String s)` → `true` si todos sus caracteres son dígitos.

---

## Parte C · Construir y transformar

- [ ] **C1** ⭐⭐ `String cifrar(String texto, int n)` y `String descifrar(String texto, int n)` con el cifrado César (solo minúsculas; lo demás queda igual).
- [ ] **C2** ⭐⭐ `String alternar(String s)` → mayúsculas y minúsculas alternadas: `"programa"` → `"PrOgRaMa"`.
- [ ] **C3** ⭐⭐ `String comprimir(String s)` → `"aaabbc"` → `"a3b2c1"`.
- [ ] **C4** ⭐⭐ `String palabraMasLarga(String frase)`
- [ ] **C5** ⭐⭐ `int sumarDigitosTexto(String s)` → `"a1b2c3"` → `6`.
- [ ] **C6** ⭐⭐⭐ `boolean sonAnagramas(String a, String b)` → `"amor"` y `"roma"` → `true`.
- [ ] **C7** ⭐⭐⭐ `String aBinarioTexto(int n)` y `int deBinario(String bin)` → `"1101"` → `13`.

> [!tip]- Pista C3
> Recorre la cadena contando cuántas veces se repite el carácter actual. Cuando cambia (o se acaba la cadena), agrega el carácter y su cuenta al resultado.

> [!tip]- Pista C6
> Dos palabras son anagramas si tienen la misma longitud y **cada letra aparece la misma cantidad de veces** en ambas. Reutiliza `contarLetra`.

---

## Parte D · Problemas tipo examen ⭐⭐⭐

- [ ] **D1 · Tiempos de lectura.** Leer un carácter toma 1 unidad de tiempo, y las palabras están separadas por **un** espacio. Escribe `String tiempos(String texto)` que devuelva cada palabra con el tiempo en que se termina de leer. Para `"este es un ejemplo"`:
  ```text
  (este, 4) (es, 7) (un, 10) (ejemplo, 18)
  ```
- [ ] **D2 · Validar contraseña.** `String validar(String clave)` → `"VÁLIDA"` si tiene al menos 8 caracteres, una mayúscula, una minúscula y un dígito; si no, indica **qué** le falta.
- [ ] **D3 · Código SIS.** Un código SIS válido tiene 9 dígitos y empieza con `20`. Escribe `boolean esCodigoValido(String cod)` y un `main` que lea códigos hasta que se ingrese `"fin"` y muestre cuántos fueron válidos.

> [!tip]- Pista D1
> Recorre el texto con un índice `i`. Cada vez que encuentres un espacio (o llegues al final), la palabra que acaba de terminar se leyó en el tiempo `i` (o `length()` al final). Ve guardando dónde empezó la palabra para sacarla con `substring`.

---

## Autoevaluación

Antes de pasar al [[Día 09 - Apuntes|Día 9]], comprueba que puedes:

- [ ] Explicar por qué los índices van de `0` a `length() - 1`.
- [ ] Usar `charAt`, `substring`, `indexOf`, `equals` y `replace` sin buscar en los apuntes.
- [ ] Recorrer una cadena con un `for` y contar o transformar sus caracteres.
- [ ] Construir una cadena nueva concatenando en un ciclo.
- [ ] Convertir texto a número con `Integer.parseInt` y número a texto con `String.valueOf`.
