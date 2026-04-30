# Bits, Semidúplex, TCP, UDP e IANA (explicación ampliada)

---

#  Conversión de unidades

## bit y byte
- 1 byte = 8 bits

## conversiones en redes
- bit × 1000 = kbit (kilobit)
- byte × 1024 = kByte (kilobyte)

### Nota importante
En redes se suele usar el sistema decimal (×1000), mientras que en memoria se usa el sistema binario (×1024).

---

# Semidúplex (Half-Duplex)

La semidúplex es un modo de comunicación donde la transmisión es bidireccional, pero no simultánea.

## Características
- Solo una señal puede transmitirse a la vez
- No permite enviar y recibir al mismo tiempo
- Es necesario alternar el uso del canal

## Ejemplos
- Walkie-talkies
- Sistemas de radio
- Canales de comunicación donde solo una emisión ocupa la frecuencia

## Idea clave
Solo se puede usar una dirección de comunicación por vez en el mismo canal.

---

# Métodos de envío

## TCP (Transmission Control Protocol)

Es un protocolo de transporte orientado a conexión que garantiza la entrega correcta de los datos.

## Características
- Control de errores
- Confirmación de recepción
- Reenvío de datos perdidos
- Orden correcto de los paquetes

## Idea clave
TCP es confiable, pero más lento debido a sus controles.

---

## Estructura del encabezado TCP

| Campo | Tamaño |
|------|--------|
| Source Port | 2 bytes |
| Destination Port | 2 bytes |
| Sequence Number | 4 bytes |
| Acknowledgment Number | 4 bytes |
| Data Offset | 4 bits |
| Reserved | 3 bits |
| Control Flags | 9 bits |
| Window Size | 2 bytes |
| Checksum | 2 bytes |
| Urgent Pointer | 2 bytes |
| Optional Data | 0–40 bytes |

### Función de campos importantes
- Sequence Number: orden de los datos
- Acknowledgment Number: confirmación de recepción
- Checksum: detección de errores
- Flags: control de la conexión

---

## UDP (User Datagram Protocol)

Es un protocolo de transporte sin conexión.

## Características
- No garantiza entrega
- No asegura orden
- Muy rápido
- Bajo consumo de recursos

## Estructura

| Campo | Tamaño |
|------|--------|
| Source Port | 2 bytes |
| Destination Port | 2 bytes |
| Length | 2 bytes |
| Checksum | 2 bytes |

Total: 8 bytes

## Uso
- Streaming
- Juegos online
- Videollamadas

---

# IANA (Internet Assigned Numbers Authority)

La IANA es la organización encargada de asignar y gestionar los números de puertos y protocolos en internet.

---

## Rangos de puertos

- 0–1024: puertos bien conocidos
- 1025–49151: puertos registrados
- 49152–65535: puertos dinámicos o privados

---

## Ejemplos de puertos

- 0: reservado
- 20 y 21 (FTP): transferencia de archivos
- 22 (SSH): acceso remoto seguro
- 23 (Telnet): acceso remoto inseguro
- 25 (SMTP): envío de correos electrónicos
- 37: servicio de tiempo
- 38: acceso a rutas
- 39 (RIP): protocolo de enrutamiento
- 42: nombres de host
- 43: servicio de consulta de usuarios
- 53 (DNS): resolución de nombres a IP
- 69 (TFTP): transferencia simple de archivos
- 80 (HTTP): web sin cifrado
- 110 (POP3): recepción de correos
- 123 (NTP): sincronización de tiempo
- 137–139 (NetBIOS): servicios de red en LAN

---

## NetBIOS (137–139)

- 137: inicio del sistema de nombres
- 138: envío de datagramas
- 139: gestión de sesiones

---

# Frecuencia y ciclo de reloj

## Frecuencia
Es la cantidad de veces que una señal se repite por segundo.

## Ciclo de reloj
Es la unidad básica de tiempo en sistemas digitales.

### Relación
- A mayor frecuencia, mayor cantidad de operaciones por segundo
- Se mide en Hertz (Hz)

---

# Resumen general

```md
# Redes y Transporte de Datos

## Unidades
- 1 byte = 8 bits
- bit × 1000 = kbit
- byte × 1024 = kByte

## Semidúplex
- Comunicación bidireccional no simultánea
- Solo una transmisión activa por vez

## TCP
- Confiable
- Control de errores
- Orden de datos garantizado

## UDP
- No confiable
- Rápido
- Sin control de orden ni entrega

## IANA
- Organiza puertos de red
- 0–1024: conocidos
- 1025–49151: registrados
- 49152–65535: privados

## Puertos importantes
- 22 SSH
- 25 SMTP
- 53 DNS
- 80 HTTP
- 110 POP3
- 123 NTP
- 137–139 NetBIOS

## Frecuencia
- Ciclo de repetición por segundo
- Medido en Hz
