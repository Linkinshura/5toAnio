# Clases, atributos y métodos

## Clase
Una clase es una plantilla que define cómo será un objeto.

Ejemplo:

```java
class Botella {

}
```

---

## Atributos
Los atributos son las características o datos que tiene un objeto.

```java
color colorBotella;
float capacidad;
float cantidadLiquido;
```

- `colorBotella` → color de la botella
- `capacidad` → capacidad máxima
- `cantidadLiquido` → cantidad actual de líquido

---

## Constructor
El constructor se ejecuta automáticamente al crear un objeto.

```java
Botella() {
    capacidad = 500;
    cantidadLiquido = 0;
}
```

- La capacidad inicia en `500`
- La cantidad de líquido inicia en `0`

---

## Métodos
Los métodos son acciones que puede realizar el objeto.

### Llenar

```java
void llenar() {
    cantidadLiquido = capacidad;
}
```

Llena completamente la botella.

### Vaciar

```java
void vaciar() {
    cantidadLiquido = 0;
}
```

Vacía la botella.

---

# Resumen

- **Clase** → plantilla del objeto
- **Atributos** → características o datos
- **Constructor** → inicializa valores
- **Métodos** → acciones del objeto