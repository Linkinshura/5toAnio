# 4. Sistemas interactivos y modelado (pre-POO)

En este último tema se integran todos los conceptos anteriores para construir sistemas visuales más complejos y dinámicos. El objetivo es pasar de estructuras de datos simples a modelos donde cada elemento tiene identidad, estado y comportamiento propio, sin llegar aún al uso formal de clases.

Se trabaja con grillas donde cada celda puede almacenar múltiples estados, utilizando estructuras como arrays bidimensionales o tridimensionales. Esto permite representar sistemas donde cada elemento tiene varias propiedades internas.

También se profundiza en la interacción avanzada, donde el usuario modifica directamente estructuras completas mediante el mouse, activando o modificando estados dentro de matrices o listas de elementos.

Se introduce la generación procedural mediante el uso de valores aleatorios, lo que permite crear sistemas que no son estáticos, sino que varían automáticamente en su construcción o comportamiento.

Otro aspecto importante es el modelado de entidades visuales, donde cada elemento contiene múltiples atributos como posición, color o tamaño, representados mediante arrays paralelos. Esto funciona como una aproximación conceptual a los objetos.

Finalmente, se trabaja con sistemas de relaciones entre elementos, como conexiones entre puntos o estructuras geométricas complejas, lo que introduce la idea de sistemas completos en lugar de elementos aislados.

---

## Ejemplo básico: grilla con estados múltiples

```java
int cols = 8;
int rows = 8;
boolean[][] estados;

float cellSize;

void setup() {
  size(400, 400);
  cellSize = width / (float)cols;

  estados = new boolean[cols][rows];
}

void draw() {
  background(255);

  for (int i = 0; i < cols; i++) {
    for (int j = 0; j < rows; j++) {

      if (estados[i][j]) {
        fill(0);
      } else {
        fill(255);
      }

      rect(i * cellSize, j * cellSize, cellSize, cellSize);
    }
  }
}

void mousePressed() {
  int i = int(mouseX / cellSize);
  int j = int(mouseY / cellSize);

  if (i >= 0 && i < cols && j >= 0 && j < rows) {
    estados[i][j] = !estados[i][j];
  }
}
