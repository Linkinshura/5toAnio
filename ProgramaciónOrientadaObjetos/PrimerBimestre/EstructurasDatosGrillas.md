# 3. Estructuras de datos y grillas

En este tema se introduce el uso de estructuras de datos para representar múltiples elementos de forma organizada, pasando de dibujos individuales a sistemas compuestos por muchas partes relacionadas.

Se trabaja principalmente con grillas bidimensionales, utilizando bucles anidados para recorrer filas y columnas. Cada celda de la grilla representa una unidad de información que puede tener un estado o comportamiento propio.

También se incorporan arrays (arreglos), tanto de una dimensión como bidimensionales, que permiten almacenar conjuntos de valores como números, posiciones o estados. Esto habilita la creación de sistemas visuales más complejos como barras, puntos o matrices de comportamiento.

Un aspecto importante es la relación entre el espacio visual y los índices de los arrays, convirtiendo posiciones del mouse en posiciones dentro de una estructura de datos. Esto permite interactuar directamente con elementos organizados en grilla.

Además, se introduce el concepto de mapeo de valores, donde magnitudes como la distancia o la posición se transforman en propiedades visuales como color o tamaño.

---

## Ejemplo básico: grilla interactiva

```java
int cols = 10;
int rows = 10;
float cellSize;

void setup() {
  size(400, 400);
  cellSize = width / (float)cols;
}

void draw() {
  background(255);

  for (int i = 0; i < cols; i++) {
    for (int j = 0; j < rows; j++) {

      float d = dist(mouseX, mouseY, i * cellSize, j * cellSize);
      float c = map(d, 0, width, 255, 0);

      fill(c);
      rect(i * cellSize, j * cellSize, cellSize, cellSize);
    }
  }
}
