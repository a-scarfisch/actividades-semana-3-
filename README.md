# actividad-arquitectura-de-redes
Actividad Bootcamp Generation 

### 🧩 1. Conceptos base

Completar tabla:

| Concepto | Definición simple | Nivel técnico breve | Ejemplo real |
| --- | --- | --- | --- |
| Modelo OSI (Open System Interconection) | Sistema de capas que permite la comunicación entre sistemas de red | Se divide el sistema de comunicación en 7 capas abstractas desde la capa física hasta la capa de aplicación.  | Como un pastel, necesita una base, rellenos y toppings.  |
| Subred (Subnet) | Segmentación de red a una más manejables  | dividir una red grande en varias redes más pequeñas y administrables mediante el uso de una máscara subred. | como la red electríca, la divides en varias secciones para que no colapsen por sobrecarga. |
| DNS(Domain Name System) | Traduce nombres y equipos a números  | Nomenclatura jerarquizada que denomina identificadores binarios a redes y dispositivos | Como las etiquetas que se le ponen a las cosas en el colegio.  |

👉 Reglas:

- Máximo 3 líneas por celda
- Explicación clara para alguien sin experiencia

---

### 🧱 2. Modelo OSI (lo justo y necesario)

Responder:

- ¿Qué es el modelo OSI?
- ¿Para qué sirve?

👉 Completar tabla:

| Capa | Nombre | ¿Qué hace? (simple) |
| --- | --- | --- |
| 1 | Física | Trasmite bits fisicamente |
| 2 | Enlace | Organización de bit  |
| 3 | Red | Enrutamiento de paquetes e IP |
| 4 | Transporte | Trasferencias de datos entre flujos |
| 5 | Sesión | Establece y gestiona conexiones |
| 6 | Presentación | Traduce cifra y comprime datos |
| 7 | Aplicación | Interfaz con el usuario |

👉 CLAVE:

- No memorizar → entender flujo

---

### 🌐 3. DNS (lo que usas todos los días)

Responder:

- ¿Qué es DNS?
    - los dominios legibles
- ¿Por qué no usamos IP directamente?
    - porque nadie se aprendería un número de memoria

👉 Explicar paso a paso:

> ¿Qué pasa cuando escribes:
> 
> 
> `google.com` en el navegador?
> 
> El buscador  traduce lo escrito a una IP para llevar al usuario a esa dirección específica. 
> 

👉 Flujo esperado:

- Usuario → DNS → IP → servidor

---

### 🧩 4. Subnets (nivel básico pero clave)

Responder:

- ¿Qué es una subred?
    - segmentación de una IP en partes más pequeñas
- ¿Para qué sirve?
    - para mejorar el rendimiento y reducir el tráfico de broadcast
- ¿Por qué dividir redes?
    - mejora la seguridad, limita la propagación de malware

👉 Ejemplo developer:

- Red local vs red en cloud

---

### 💻 5. Conexión directa con desarrollo (CRÍTICO)

Responder:

- ¿Qué pasa cuando tu app:
    - No encuentra el servidor?
        - problema de conexión
    - No resuelve el dominio?
        - No traduce el IP
    - No puede conectarse?
        - error del servidor o puerto

👉 Relacionar con:

- DNS
- IP
- Red

---

### 🚨 6. Problemas reales (debugging)

Responder:

- ¿Qué significa:
    - “DNS not found”?
        - no sabe a que dominio pertenece esa IP
    - “Host unreachable”?
        - reconoce el IP, no sabe como llegar al servidor
    - “Network error”?
        - corte de comunicación de red
- ¿Qué revisarías primero como developer?
    - consola del navegador, para ver el error exacto
    - errores de tipeo, revisar URL
    - revisar conexión internet

---

### 🌍 7. Caso práctico real

Escenario:

> “Tu aplicación está deployada, pero nadie puede acceder”
> 

Responder:

- ¿Es problema de DNS?
    - Es que el nombre aún no apunta a tu servidor. Puede que sea nuevo y la propagación es lenta.
- ¿Es problema de red?
    - El servidor puede estar encendido, pero tiene las "fronteras" cerradas.
- ¿Es problema de configuración?
    - esta en la red local, hay que configurarlo para que acepte conexiones externas.

---

### 🧪 8. Analogía obligatoria

Crear analogía:

| Concepto | Analogía |
| --- | --- |
| OSI | Biblioteca universitaria  |
| DNS | Número del sistema Dewey  |
| Subnet | Colección especifica de libros  |

👉 Ejemplo esperado:

- OSI = proceso de envío de paquete paso a paso
- DNS = agenda de contactos
- Subnet = barrios dentro de una ciudad
