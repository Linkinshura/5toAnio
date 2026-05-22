# Arrays en Processing

## ¿Qué es un Array?

Un **array** es una estructura que permite guardar muchos datos del mismo tipo dentro de una sola variable.

Ejemplo sin array:

```java
int nota1 = 7;
int nota2 = 10;
int nota3 = 5;
```

Ejemplo con array:

```java
int[] notas = {7, 10, 5};
```

Cada dato tiene una posición llamada **índice**.

| Índice | Valor |
|---|---|
| 0 | 7 |
| 1 | 10 |
| 2 | 5 |

---

# Arrays de 2 Dimensiones

También llamados **matrices**.

Sirven para representar tablas, mapas, tableros, píxeles, etc.

Se usan con:

```java
tipo[][] nombre;
```

Ejemplo:

```java
int[][] tablero = new int[3][4];
```

Esto crea:

- 3 filas
- 4 columnas

Visualmente:

|   |   |   |   |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |

---

## Acceder a posiciones

```java
tablero[1][2] = 5;
```

Significa:

- fila 1
- columna 2

Resultado:

|   |   |   |   |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 5 | 0 |
| 0 | 0 | 0 | 0 |

---

## Recorrer arrays 2D

Se usan dos `for`.

```java
for (int f = 0; f < 3; f++) {
  for (int c = 0; c < 4; c++) {
    println(tablero[f][c]);
  }
}
```

- Primer `for` → filas
- Segundo `for` → columnas

---

## Ejemplo práctico: Dibujar una cuadrícula

```java
int[][] mapa = new int[10][10];

void setup() {
  size(400, 400);
}

void draw() {
  background(255);

  int tam = 40;

  for (int f = 0; f < 10; f++) {
    for (int c = 0; c < 10; c++) {

      if (mapa[f][c] == 0) {
        fill(255);
      } else {
        fill(0);
      }

      rect(c * tam, f * tam, tam, tam);
    }
  }
}
```

---

# Arrays de 3 Dimensiones

Son arrays dentro de arrays dentro de arrays.

Se usan con:

```java
tipo[][][] nombre;
```

Ejemplo:

```java
int[][][] datos = new int[2][3][4];
```

Esto significa:

- 2 capas
- 3 filas
- 4 columnas

---

## Visualización

Podés imaginarlo como varios tableros 2D apilados.

### Capa 0

|   |   |   |   |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |

### Capa 1

|   |   |   |   |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 |

---

## Acceder a datos

```java
datos[1][2][3] = 9;
```

Significa:

- capa 1
- fila 2
- columna 3

---

## Recorrer arrays 3D

Se necesitan tres `for`.

```java
for (int z = 0; z < 2; z++) {
  for (int f = 0; f < 3; f++) {
    for (int c = 0; c < 4; c++) {

      println(datos[z][f][c]);

    }
  }
}
```

---

# Arrays Booleanos

Los arrays booleanos guardan solamente:

- `true`
- `false`

Muy útiles para:

- colisiones
- estados
- teclas
- casillas activadas
- paredes
- celdas ocupadas

---

## Array booleano normal

```java
boolean[] botones = new boolean[5];
```

Todos empiezan en `false`.

---

## Cambiar valores

```java
botones[2] = true;
```

---

## Verificar

```java
if (botones[2]) {
  println("Activado");
}
```

Es equivalente a:

```java
if (botones[2] == true)
```

---

# Arrays Booleanos 2D

Muy usados en juegos.

Ejemplo:

```java
boolean[][] paredes = new boolean[10][10];
```

Cada celda puede ser:

- `true` → hay pared
- `false` → vacío

---

## Ejemplo visual

```java
boolean[][] celdas = new boolean[8][8];

void setup() {
  size(400, 400);

  celdas[2][3] = true;
  celdas[5][1] = true;
}

void draw() {

  int tam = 50;

  for (int f = 0; f < 8; f++) {
    for (int c = 0; c < 8; c++) {

      if (celdas[f][c]) {
        fill(0);
      } else {
        fill(255);
      }

      rect(c * tam, f * tam, tam, tam);
    }
  }
}
```

---

# Diferencias rápidas

| Tipo | Ejemplo | Uso |
|---|---|---|
| 1D | `int[]` | Lista |
| 2D | `int[][]` | Tableros, mapas |
| 3D | `int[][][]` | Capas, mundos |
| Boolean | `boolean[]` | Estados verdadero/falso |

---

# Conceptos importantes

## Índices

Los arrays empiezan en `0`.

```java
int[] nums = new int[5];
```

Posiciones válidas:

```java
0
1
2
3
4
```

---

## length

Devuelve tamaño del array.

```java
println(nums.length);
```

---

## Error común

```java
nums[5] = 10;
```

Da error porque la última posición es `4`.

---

# Ejemplo combinando todo

```java
int filas = 5;
int columnas = 5;

boolean[][] tablero = new boolean[filas][columnas];

void setup() {
  size(500, 500);

  tablero[1][1] = true;
  tablero[2][3] = true;
  tablero[4][0] = true;
}

void draw() {

  background(220);

  int tam = width / columnas;

  for (int f = 0; f < filas; f++) {

    for (int c = 0; c < columnas; c++) {

      if (tablero[f][c]) {
        fill(0, 255, 0);
      } else {
        fill(255);
      }

      rect(c * tam, f * tam, tam, tam);
    }
  }
}
```