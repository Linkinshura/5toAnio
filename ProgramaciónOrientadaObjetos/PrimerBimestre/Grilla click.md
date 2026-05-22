# Grilla interactiva en Processing

Una **grilla** es una matriz de celdas organizadas en filas y columnas.  
Cada celda puede guardar un valor, por ejemplo:

- `true` → rojo
- `false` → blanco

Cuando hacemos click sobre una celda:
- si estaba blanca → pasa a roja
- si estaba roja → vuelve a blanca

---

# Conceptos importantes

## 1. Array bidimensional

Se usa un array de 2 dimensiones para guardar el estado de cada celda.

```java
boolean[][] grilla;
```

- Primer índice → fila
- Segundo índice → columna

Ejemplo:

```java
grilla[2][3]
```

Significa:
- fila 2
- columna 3

---

# Cómo detectar la celda clickeada

La posición del mouse se transforma en fila y columna usando división:

```java
int col = mouseX / tamCelda;
int fil = mouseY / tamCelda;
```

Si cada celda mide `50` píxeles:

- mouseX = 120
- 120 / 50 = 2

Entonces el click fue en la columna 2.

---

# Cambiar entre rojo y blanco

Se usa el operador `!` para invertir booleanos.

```java
grilla[fil][col] = !grilla[fil][col];
```

Funciona así:

- `true` → `false`
- `false` → `true`

---

# Ejemplo completo

```java
int filas = 6;
int columnas = 8;

int tamCelda = 60;

boolean[][] grilla = new boolean[filas][columnas];

void setup() {
  size(480, 360);
}

void draw() {
  background(220);

  for (int f = 0; f < filas; f++) {
    for (int c = 0; c < columnas; c++) {

      if (grilla[f][c]) {
        fill(255, 0, 0);
      } else {
        fill(255);
      }

      rect(c * tamCelda, f * tamCelda, tamCelda, tamCelda);
    }
  }
}

void mousePressed() {

  int col = mouseX / tamCelda;
  int fil = mouseY / tamCelda;

  if (fil >= 0 && fil < filas &&
      col >= 0 && col < columnas) {

    grilla[fil][col] = !grilla[fil][col];
  }
}
```

---

# Explicación del código

## Crear la grilla

```java
boolean[][] grilla = new boolean[filas][columnas];
```

Todas las celdas empiezan en `false` (blancas).

---

## Dibujar la grilla

```java
for (int f = 0; f < filas; f++) {
  for (int c = 0; c < columnas; c++) {
```

Recorre todas las filas y columnas.

---

## Cambiar color

```java
if (grilla[f][c]) {
  fill(255, 0, 0);
} else {
  fill(255);
}
```

- `true` → rojo
- `false` → blanco

---

## Dibujar cada celda

```java
rect(c * tamCelda, f * tamCelda, tamCelda, tamCelda);
```

La posición depende de:
- columna
- fila
- tamaño de celda

---

## Detectar click

```java
int col = mouseX / tamCelda;
int fil = mouseY / tamCelda;
```

Convierte píxeles del mouse en índices de la matriz.

---

## Cambiar estado

```java
grilla[fil][col] = !grilla[fil][col];
```

Invierte el valor:
- blanco ↔ rojo

---

# Resultado

La grilla funciona como un tablero interactivo:

- Click → rojo
- Otro click → blanco
- Cada celda guarda su propio estado usando booleanos.