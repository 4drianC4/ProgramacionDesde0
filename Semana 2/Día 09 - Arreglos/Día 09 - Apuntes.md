---
tipo: apuntes
dia: 9
semana: 2
tema: Arreglos
tags: [java, intro-programacion, dia-09, apuntes]
---

# Día 9 · Arreglos

> [!info] Datos de la clase
> **Semana 2 · Jueves** · **IDE:** BlueJ · **Requisito:** [[Día 08 - Apuntes|Día 8]]
> **Material del día:** [[Día 09 - Diapositivas|Diapositivas]] · [[Día 09 - Práctica|Práctica]] · [[README|Ruta de aprendizaje]]

> [!abstract] Al terminar este día podrás…
> - **Declarar, crear y recorrer** arreglos.
> - Resolver los algoritmos clásicos: **suma, promedio, máximo, mínimo, búsqueda y conteo**.
> - Pasar arreglos a **métodos** y devolverlos.
> - Usar **arreglos paralelos**.
> - Usar un arreglo como **atributo** de una clase para **agregar, buscar y eliminar** elementos.
> - **Ordenar** un arreglo con el método de la burbuja.

---

### 1. ¿Por qué arreglos?

Si necesitas las notas de 40 estudiantes, no vas a declarar `nota1`, `nota2`, …, `nota40`. Un **arreglo** (*array*) guarda **muchos valores del mismo tipo** bajo **un solo nombre**, y cada valor se identifica por su **posición** (índice).

| Índice | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| `notas` | 75 | 48 | 91 | 60 | 33 |

- `notas[0]` vale 75, `notas[2]` vale 91.
- Igual que en los `String` ([[Día 08 - Apuntes#2. Índices, las posiciones de una cadena|Día 8]]), los índices van de **0** a **`length - 1`**.

### 2. Declarar y crear

```java
int[] notas = new int[5];                  // 5 enteros, todos en 0
double[] precios = new double[100];         // 100 doubles, todos en 0.0
String[] nombres = new String[40];          // 40 String, todos en null
int[] primos = {2, 3, 5, 7, 11};            // creado con valores
```

| Parte | Significa |
|---|---|
| `int[]` | "arreglo de `int`" (el tipo) |
| `new int[5]` | crea espacio para **5** enteros |
| `{2, 3, 5}` | crea el arreglo con esos valores (solo al declararlo) |
| `notas.length` | la cantidad de casillas (**sin** paréntesis, a diferencia de `String`) |

> [!important] El tamaño es fijo
> Una vez creado, un arreglo **no cambia de tamaño**. Si necesitas "agregar" elementos, se crea con un tamaño máximo y se lleva un **contador** de cuántos están ocupados (§9).

**Valores por defecto:** `0` para números, `false` para `boolean`, `'\u0000'` para `char` y `null` para objetos (como `String`).

### 3. Acceder a las casillas

```java
notas[0] = 75;                 // guardar
notas[1] = notas[0] - 27;      // leer y guardar
System.out.println(notas[1]);  // 48
```

> [!danger] `ArrayIndexOutOfBoundsException`
> `notas[5]` en un arreglo de 5 casillas es un error: el último índice es **4**. Es el error más común con arreglos; revisa siempre que el ciclo use `i < arreglo.length`.

### 4. Recorrer un arreglo

El patrón de siempre: un `for` de `0` a `length - 1`.

```java
// Leer
Scanner sc = new Scanner(System.in);
int[] notas = new int[5];
for (int i = 0; i < notas.length; i++) {
    System.out.print("Nota " + (i + 1) + ": ");
    notas[i] = sc.nextInt();
}

// Mostrar
for (int i = 0; i < notas.length; i++) {
    System.out.println("notas[" + i + "] = " + notas[i]);
}
```

**`for-each`:** cuando solo necesitas **leer** cada valor (sin el índice):

```java
int suma = 0;
for (int n : notas) {     // "para cada n en notas"
    suma += n;
}
```

> [!tip] Mostrar un arreglo rápido
> `java.util.Arrays.toString(notas)` devuelve `"[75, 48, 91, 60, 33]"`. Útil para probar.

### 5. Algoritmos clásicos

```java
public double promedio(int[] a) {
    int suma = 0;
    for (int i = 0; i < a.length; i++) {
        suma += a[i];
    }
    return (double) suma / a.length;
}

public int maximo(int[] a) {
    int max = a[0];                    // empieza con el PRIMER elemento
    for (int i = 1; i < a.length; i++) {
        if (a[i] > max) {
            max = a[i];
        }
    }
    return max;
}

public int posicionDelMinimo(int[] a) {
    int pos = 0;
    for (int i = 1; i < a.length; i++) {
        if (a[i] < a[pos]) {
            pos = i;
        }
    }
    return pos;
}

public int contarAprobados(int[] notas) {
    int cont = 0;
    for (int n : notas) {
        if (n >= 51) {
            cont++;
        }
    }
    return cont;
}
```

> [!warning] ¿Por qué el máximo empieza en `a[0]` y no en `0`?
> Si todos los valores fueran negativos, empezar en `0` daría un máximo que **no está** en el arreglo.

### 6. Búsqueda secuencial

Recorre el arreglo hasta **encontrar** el valor; devuelve su posición o `-1` si no está.

```java
public int buscar(int[] a, int x) {
    int pos = -1;
    int i = 0;
    while (i < a.length && pos == -1) {
        if (a[i] == x) {
            pos = i;
        }
        i++;
    }
    return pos;
}
```

Con `String` se compara con `equals`: `if (nombres[i].equals(buscado))`.

### 7. Arreglos y métodos

Un arreglo puede ser **parámetro** y también **valor de retorno**:

```java
public int[] invertido(int[] a) {
    int[] r = new int[a.length];
    for (int i = 0; i < a.length; i++) {
        r[i] = a[a.length - 1 - i];
    }
    return r;
}
```

> [!important] Un método **puede modificar** el arreglo que recibe
> Con un `int` el método recibe una **copia** del valor. Con un arreglo recibe una **referencia** al mismo arreglo: si cambia una casilla, el cambio se ve afuera.
> ```java
> public void duplicar(int[] a) {
>     for (int i = 0; i < a.length; i++) {
>         a[i] = a[i] * 2;      // modifica el arreglo original
>     }
> }
> ```

### 8. Arreglos paralelos

Varios arreglos del **mismo tamaño** donde la **misma posición** corresponde al **mismo elemento**:

| `i` | `nombres[i]` | `notas[i]` |
|---|---|---|
| 0 | Ana | 75 |
| 1 | Luis | 48 |
| 2 | Rosa | 91 |

```java
public String mejorEstudiante(String[] nombres, int[] notas) {
    int pos = 0;
    for (int i = 1; i < notas.length; i++) {
        if (notas[i] > notas[pos]) {
            pos = i;
        }
    }
    return nombres[pos] + " con " + notas[pos];
}
```

### 9. Un arreglo como atributo: agregar, buscar y eliminar

Para una colección que **crece y se achica** (hasta un máximo), se usa un arreglo **más un contador** de elementos ocupados.

```java
public class ListaNotas {
    private int[] notas;
    private int cantidad;                 // cuántas casillas están ocupadas

    public ListaNotas(int maximo) {
        notas = new int[maximo];
        cantidad = 0;
    }

    public boolean agregar(int nota) {
        boolean ok = cantidad < notas.length;
        if (ok) {
            notas[cantidad] = nota;       // la primera casilla libre
            cantidad++;
        }
        return ok;
    }

    public boolean eliminar(int pos) {
        boolean ok = pos >= 0 && pos < cantidad;
        if (ok) {
            for (int i = pos; i < cantidad - 1; i++) {
                notas[i] = notas[i + 1];  // desplazar a la izquierda
            }
            cantidad--;
        }
        return ok;
    }
}
```

```text
Eliminar la posición 1 de [75, 48, 91, 60] (cantidad = 4):
[75, 91, 91, 60]  →  [75, 91, 60, 60]  →  cantidad = 3  →  [75, 91, 60]
```

> [!tip] Recorre solo hasta `cantidad`
> En esta clase, los ciclos van de `0` a `cantidad - 1`, **no** hasta `notas.length`: las casillas siguientes no tienen datos válidos.

### 10. Ordenar: el método de la burbuja

Compara cada par de vecinos y los **intercambia** si están en el orden incorrecto. Después de cada pasada, el mayor "sube" al final.

```java
public void ordenar(int[] a) {
    for (int pasada = 0; pasada < a.length - 1; pasada++) {
        for (int i = 0; i < a.length - 1 - pasada; i++) {
            if (a[i] > a[i + 1]) {
                int aux = a[i];           // intercambio con auxiliar
                a[i] = a[i + 1];
                a[i + 1] = aux;
            }
        }
    }
}
```

| Pasada | Arreglo |
|---|---|
| inicio | `[5, 1, 4, 2]` |
| 1 | `[1, 4, 2, 5]` |
| 2 | `[1, 2, 4, 5]` |
| 3 | `[1, 2, 4, 5]` |

> [!tip] Variantes
> - **Descendente:** cambia `>` por `<`.
> - **`String` por orden alfabético:** `if (a[i].compareTo(a[i + 1]) > 0)`.
> - **Arreglos paralelos:** cuando intercambies en uno, intercambia **también** en los otros.

---

## Resumen

> [!summary] Lo esencial del Día 9
> - `int[] a = new int[n];` crea `n` casillas; `a.length` es su tamaño (fijo). Índices de `0` a `length - 1`.
> - Recorrer: `for (int i = 0; i < a.length; i++)`; solo leer: `for (int x : a)`.
> - Máximo y mínimo empiezan con `a[0]`; la búsqueda devuelve la posición o `-1`.
> - Un método que recibe un arreglo **puede modificarlo**.
> - Arreglos paralelos: la misma posición es el mismo elemento.
> - Colección con arreglo: arreglo + **contador**; eliminar = desplazar a la izquierda.
> - Burbuja: comparar vecinos e intercambiar con una variable auxiliar.

## Siguiente paso

- ✍️ Practica: [[Día 09 - Práctica]]
- 📖 Glosario: [[Glosario]]
- ⬅️ Ayer: [[Día 08 - Apuntes|Día 8 · Cadenas]]
- ➡️ Mañana: [[Día 10 - Apuntes|Día 10 · Matrices e integrador]]
