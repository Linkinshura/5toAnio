# Subneteo - Resumen

## ¿Qué es el subneteo?

El subneteo consiste en dividir una red IP grande en varias subredes más pequeñas para mejorar la organización, la administración y el aprovechamiento de las direcciones IP.

## Conceptos importantes

- **Dirección de red:** primera IP de una subred.
- **Broadcast:** última IP de una subred.
- **Hosts válidos:** direcciones utilizables por dispositivos.
- **Máscara de subred:** define qué parte de la IP corresponde a la red y cuál a los hosts.
- **Gateway:** dirección IP del router dentro de una subred.

## Fórmulas principales

### Hosts válidos

```txt
2^h - 2
```

### Cantidad de subredes

```txt
2^s
```

### Tamaño del salto

```txt
256 - máscara
```

## Máscaras más comunes

| CIDR | Máscara | Hosts |
|-------|---------|---------|
| /24 | 255.255.255.0 | 254 |
| /25 | 255.255.255.128 | 126 |
| /26 | 255.255.255.192 | 62 |
| /27 | 255.255.255.224 | 30 |
| /28 | 255.255.255.240 | 14 |
| /29 | 255.255.255.248 | 6 |

---

# Ejercicio Resuelto

## Datos

Red:

```txt
10.0.0.0/24
```

Hosts necesarios:

```txt
25 hosts por subred
```

---

## Paso 1 - Calcular hosts

Aplicamos:

```txt
2^h - 2
```

| Bits Host | Resultado | ¿Alcanza? |
|------------|------------|------------|
| 4 | 14 | ❌ |
| 5 | 30 | ✅ |

Se necesitan:

```txt
5 bits para hosts
```

---

## Paso 2 - Calcular máscara

IPv4 posee:

```txt
32 bits
```

Entonces:

```txt
32 - 5 = 27
```

Nueva máscara:

```txt
/27
```

Máscara decimal:

```txt
255.255.255.224
```

---

## Paso 3 - Calcular subredes

La red original era:

```txt
/24
```

La nueva es:

```txt
/27
```

Bits prestados:

```txt
27 - 24 = 3
```

Cantidad de subredes:

```txt
2^3 = 8
```

---

## Paso 4 - Calcular salto

```txt
256 - 224 = 32
```

Salto:

```txt
32
```

---

## Paso 5 - Generar subredes

Las redes avanzan de 32 en 32:

```txt
0
32
64
96
128
160
192
224
```

---

## Subred 1

Red:

```txt
10.0.0.0
```

Hosts válidos:

```txt
10.0.0.1 - 10.0.0.30
```

Broadcast:

```txt
10.0.0.31
```

---

## Subred 2

Red:

```txt
10.0.0.32
```

Hosts válidos:

```txt
10.0.0.33 - 10.0.0.62
```

Broadcast:

```txt
10.0.0.63
```

---

## Subred 3

Red:

```txt
10.0.0.64
```

Hosts válidos:

```txt
10.0.0.65 - 10.0.0.94
```

Broadcast:

```txt
10.0.0.95
```

---

## Subred 4

Red:

```txt
10.0.0.96
```

Hosts válidos:

```txt
10.0.0.97 - 10.0.0.126
```

Broadcast:

```txt
10.0.0.127
```

---

## Subred 5

Red:

```txt
10.0.0.128
```

Hosts válidos:

```txt
10.0.0.129 - 10.0.0.158
```

Broadcast:

```txt
10.0.0.159
```

---

## Subred 6

Red:

```txt
10.0.0.160
```

Hosts válidos:

```txt
10.0.0.161 - 10.0.0.190
```

Broadcast:

```txt
10.0.0.191
```

---

## Subred 7

Red:

```txt
10.0.0.192
```

Hosts válidos:

```txt
10.0.0.193 - 10.0.0.222
```

Broadcast:

```txt
10.0.0.223
```

---

## Subred 8

Red:

```txt
10.0.0.224
```

Hosts válidos:

```txt
10.0.0.225 - 10.0.0.254
```

Broadcast:

```txt
10.0.0.255
```

---

## Tabla Final

| Subred | Hosts válidos | Broadcast |
|---------|--------------|------------|
| 10.0.0.0 | 10.0.0.1 - 10.0.0.30 | 10.0.0.31 |
| 10.0.0.32 | 10.0.0.33 - 10.0.0.62 | 10.0.0.63 |
| 10.0.0.64 | 10.0.0.65 - 10.0.0.94 | 10.0.0.95 |
| 10.0.0.96 | 10.0.0.97 - 10.0.0.126 | 10.0.0.127 |
| 10.0.0.128 | 10.0.0.129 - 10.0.0.158 | 10.0.0.159 |
| 10.0.0.160 | 10.0.0.161 - 10.0.0.190 | 10.0.0.191 |
| 10.0.0.192 | 10.0.0.193 - 10.0.0.222 | 10.0.0.223 |
| 10.0.0.224 | 10.0.0.225 - 10.0.0.254 | 10.0.0.255 |

---

## Resumen Final

Para una red **10.0.0.0/24** que necesita **25 hosts por subred**:

- Bits para hosts: **5**
- Máscara: **/27**
- Máscara decimal: **255.255.255.224**
- Hosts por subred: **30**
- Bits prestados: **3**
- Cantidad de subredes: **8**
- Salto: **32**