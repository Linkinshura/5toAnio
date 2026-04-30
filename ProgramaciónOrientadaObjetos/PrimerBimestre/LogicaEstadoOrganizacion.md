# 2. Lógica, estado y organización

En este tema se profundiza en cómo hacer que un programa no sea solo estático, sino que pueda cambiar en el tiempo y organizar mejor su estructura interna. Se introduce la idea de estado, es decir, variables que conservan su valor entre un frame y otro y permiten generar comportamiento dinámico.

A partir de esto se trabaja con animación básica, modificando variables en cada ejecución del `draw()`. Esto permite crear efectos como crecimiento, movimiento o transformación progresiva de figuras.

También se incorporan eventos de interacción más completos, como la detección de cuándo el mouse está presionado o liberado, lo que permite controlar el flujo del programa según acciones del usuario.

En paralelo, se introducen funciones con parámetros, lo que permite reutilizar código con distintos valores de entrada. Esto facilita la creación de elementos más flexibles y reutilizables.

Finalmente, se comienza a organizar el código en módulos o funciones más grandes que representan elementos del mundo visual (como casas, calles o composiciones), junto con el uso de estructuras repetitivas como bucles para generar patrones.

---

## Ejemplo básico: animación con estado

```java
int radio = 0;

void setup() {
  size(400, 400);
}

void draw() {
  background(255);

  if (mousePressed) {
    radio++;
  }

  ellipse(width/2, height/2, radio, radio);
}

void mouseReleased() {
  radio = 0;
}
