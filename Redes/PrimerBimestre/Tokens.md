# Tokens, Seguridad y Protocolos de Red (explicación ampliada)

En redes y comunicaciones, un **token** es un mecanismo lógico de control que organiza el acceso, el orden y el estado de una comunicación entre dispositivos o procesos. Se usa para evitar conflictos, mantener sincronización y permitir recuperación ante errores.

---

# Tokens (en comunicación de red)

## Token de datos
Es el elemento que inicia la comunicación y determina qué dispositivo tiene permiso para transmitir primero.

### Función:
- Asigna el turno de envío
- Evita colisiones en la red
- Controla el acceso al medio

### Idea clave:
Solo el dispositivo que posee el token puede enviar datos.

---

## Token de actividad
Organiza la comunicación en tareas o etapas.

### Función:
- Divide el proceso en actividades
- Permite retomar procesos interrumpidos
- Guarda el estado de la comunicación

### Ejemplo:
Si una transmisión se interrumpe, permite continuar desde el punto donde quedó.

---

## Token de sincronización
Mantiene el orden correcto de las operaciones dentro de la comunicación.

### Función:
- Numera o identifica actividades
- Mantiene la secuencia de datos
- Permite recuperación ante fallos
- Puede redirigir la comunicación si hay errores

### Idea clave:
Actúa como mecanismo de control de orden y continuidad.

---

## Token de finalización
Cierra la comunicación de forma controlada.

### Función:
- Termina la sesión
- Libera recursos del sistema
- Evita conexiones abiertas innecesarias
- Se activa al finalizar correctamente o ante errores

---

# Seguridad en la comunicación: SSL y TLS

## SSL (Secure Sockets Layer)
Es un protocolo antiguo que cifra la comunicación entre cliente y servidor.

### Función:
- Cifrar datos transmitidos
- Evitar interceptación de información
- Proteger la comunicación web

### Estado actual:
Está obsoleto y ha sido reemplazado.

---

## TLS (Transport Layer Security)
Es el protocolo moderno que reemplaza SSL y es el estándar actual.

### Función:
- Cifrado de datos en tránsito
- Integridad de la información
- Autenticación del servidor

### Handshake:
Proceso inicial donde:
- Se negocian algoritmos de cifrado
- Se establecen claves seguras
- Se autentica la conexión

---

## Diferencia SSL vs TLS
- SSL: base histórica del cifrado en internet
- TLS: implementación moderna, segura y actual

En la práctica, lo que se llama SSL hoy en día es TLS.

---

# Códigos HTTP (estado del servidor)

## HTTP 200
La solicitud fue procesada correctamente.

## HTTP 204
La solicitud fue correcta, pero no hay contenido para devolver.

## HTTP 404
El recurso solicitado no existe o no fue encontrado.

## HTTP 504
El servidor no recibió respuesta a tiempo de otro servidor necesario para completar la solicitud.

---

# Protocolos relacionados

## PAP (Password Authentication Protocol)
Método básico de autenticación en redes PPP.

### Características:
- Usa usuario y contraseña
- Envía credenciales en texto plano
- Baja seguridad

---

## NetBIOS (Network Basic Input/Output System)
Protocolo de capa de sesión del modelo OSI.

### Función:
- Permite comunicación entre equipos en una red local
- Facilita el uso compartido de recursos como archivos e impresoras

---

## ZIP
Formato de compresión de archivos.

### Función:
- Reduce el tamaño de archivos
- Agrupa múltiples archivos en uno solo
- Optimiza transferencias

---

## SCP (Secure Copy Protocol)
Protocolo para transferencia segura de archivos.

### Función:
- Transfiere archivos entre equipos locales y remotos
- Utiliza SSH para cifrado
- Garantiza autenticación y seguridad

---
