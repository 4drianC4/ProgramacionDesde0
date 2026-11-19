---
tipo: diapositivas
dia: 9
semana: 2
tags: [java, intro-programacion, dia-09, diapositivas]
theme: white
transition: slide
---

# Día 9

## Arreglos

**Programación desde 0** · Semana 2 · Jueves

---

# Hoy vamos a…

1. **Crear y recorrer** arreglos
2. Suma, promedio, **máximo**, **búsqueda**
3. Arreglos y **métodos**
4. Arreglos **paralelos**
5. **Agregar, eliminar** y **ordenar**

Apuntes completos: [[Día 09 - Apuntes]]

---

# ¿Por qué arreglos?

Muchos valores del **mismo tipo** con **un solo nombre**:

| 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| 75 | 48 | 91 | 60 | 33 |

`notas[2]` → `91`

---

# Crear

```java
int[] notas = new int[5];        // 5 ceros
String[] nombres = new String[40];
int[] primos = {2, 3, 5, 7, 11};
```

- `notas.length` → **5** (sin paréntesis)
- El tamaño es **fijo**

---

# Acceder

```java
notas[0] = 75;
notas[1] = notas[0] - 27;
```

> [!danger] Fuera de rango
> `notas[5]` en un arreglo de 5 → `ArrayIndexOutOfBoundsException`

---

# Recorrer

```java
for (int i = 0; i < notas.length; i++) {
    notas[i] = sc.nextInt();
}
```

Solo leer:

```java
for (int n : notas) {
    suma += n;
}
```

---

# Máximo

```java
int max = a[0];          // ¡el primero, no 0!
for (int i = 1; i < a.length; i++) {
    if (a[i] > max) {
        max = a[i];
    }
}
```

---

# Búsqueda secuencial

```java
int pos = -1, i = 0;
while (i < a.length && pos == -1) {
    if (a[i] == x) {
        pos = i;
    }
    i++;
}
```

Devuelve la posición o **-1**.

---

# Arreglos y métodos

```java
public void duplicar(int[] a) {
    for (int i = 0; i < a.length; i++) {
        a[i] *= 2;
    }
}
```

> [!important] Referencia
> El método recibe **el mismo** arreglo: los cambios se ven afuera.

---

# Arreglos paralelos

| i | nombres | notas |
|---|---|---|
| 0 | Ana | 75 |
| 1 | Luis | 48 |
| 2 | Rosa | 91 |

La **misma posición** = el **mismo** estudiante.

---

# Arreglo + contador

```java
private int[] notas;
private int cantidad;

public boolean agregar(int nota) {
    boolean ok = cantidad < notas.length;
    if (ok) {
        notas[cantidad] = nota;
        cantidad++;
    }
    return ok;
}
```

---

# Eliminar

Desplazar a la izquierda desde `pos`:

```java
for (int i = pos; i < cantidad - 1; i++) {
    notas[i] = notas[i + 1];
}
cantidad--;
```

---

# Burbuja

```java
for (int p = 0; p < a.length - 1; p++)
    for (int i = 0; i < a.length - 1 - p; i++)
        if (a[i] > a[i + 1]) {
            int aux = a[i];
            a[i] = a[i + 1];
            a[i + 1] = aux;
        }
```

---

# Burbuja paso a paso

| Pasada | Arreglo |
|---|---|
| inicio | `[5, 1, 4, 2]` |
| 1 | `[1, 4, 2, 5]` |
| 2 | `[1, 2, 4, 5]` |

Descendente: `<` · `String`: `compareTo`

---

# Resumen

- `new int[n]` · `a.length` · índices `0` a `length - 1`
- Máximo empieza en `a[0]` · búsqueda devuelve `-1`
- Los métodos **pueden modificar** el arreglo
- Paralelos: misma posición, mismo elemento
- Arreglo + contador · burbuja con `aux`

---

# Tu turno

✍️ [[Día 09 - Práctica]]

➡️ Mañana: **matrices e integrador**
