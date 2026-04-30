# 1. Fundamentos de programación gráfica

Este tema introduce las bases de la programación visual en Processing, entendiendo cómo se construyen imágenes a partir de instrucciones de código. El objetivo es aprender a controlar la pantalla como un espacio bidimensional donde cada elemento tiene posición, forma y color.

Se trabaja con la estructura principal del programa:

- `setup()`: se ejecuta una sola vez al iniciar el programa y se utiliza para configurar el entorno.
- `draw()`: se ejecuta continuamente y permite actualizar lo que se muestra en pantalla.

A partir de esto, se introduce el sistema de coordenadas, donde el origen (0,0) se encuentra en la esquina superior izquierda, y los valores de x e y determinan la posición de los elementos.

También se incorporan figuras básicas como:

- `rect()` para rectángulos  
- `ellipse()` para círculos  
- `line()` para líneas  
- `point()` para puntos  

Además, se aprende a controlar el color con `fill()` y `stroke()`, y el fondo con `background()`.

Se agregan las primeras nociones de interacción utilizando el mouse, con variables como `mouseX`, `mouseY` y eventos como `mousePressed`.

---

## Ejemplo básico

```java
void setup() {
  size(400, 400);
}

void draw() {
  background(255);

  // Dibujo de un círculo que sigue el mouse
  fill(100, 150, 255);
  ellipse(mouseX, mouseY, 50, 50);

  // Línea desde el centro a la posición del mouse
  line(width/2, height/2, mouseX, mouseY);

  // Rectángulo fijo
  fill(200, 100, 100);
  rect(100, 100, 80, 80);
}
