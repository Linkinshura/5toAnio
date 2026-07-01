# Subneteo explicacion base

## Clases:

Clase A ---> 1-126

Clase B ---> 128-191

Clase C ---> 192-224

### Privadas(usadas en ejercicios)

Clase A ---> 10.0.0.0

Clase B ---> 172.16.0.0

Clase C ---> 192.168.0.0

---
### Ejemplo

#### AND

192.168.000.000
AND
255.255.255.000

192.168.0.(000)---> subred (00000) ----> host

#### Hosts: 30

2ⁿ - 2 = 30
2ⁿ = 32
n = 5

#### Mascara de subred

255.255.255.224
224 = bits subred(2⁵ + 2⁶ + 2⁷)

2ⁿ ≥ subred(8)

#### Tabla

| Origen | Direcciones Asignables | Broadcasting |
| :-:    | :-:                    | :-:          |
|192.168.0.0 | 192.168.0.1 - 192.168.0.30 | 192.168.0.31 |
| 192.168.0.32 | 192.168.0.33 - 192.168.0.62 | 192.168.0.63 |

#### Salto

Clase C ---> cantidad de host

Clase A,B ---> 256 - ultimo octeto de mascara


