### 🧩 1. Conceptos base (definir con precisión)

Completar tabla:

| Concepto | Definición simple | Nivel técnico breve | Ejemplo real |
| --- | --- | --- | --- |
| Permissions | Reglas que definen lo que puede hacer el usuario  | Control de acceso basado en roles o atributos  | Un editor puede borrar artículos, pero un lector solo puede verlos. |
| Password segura | Una llave difícil de descifrar por una máquina | Cadena de caracteres diseñada para resistir el descifrado mediante algoritmos.  | `8kL#pQ2!vZ9x` es robusta; `123456` es una vulnerabilidad. |
| Vulnerabilidad | Debilidad, falla o error que pueden ser explotados por atacantes | Brecha en la lógica de seguridad o falta de actualización.  | Dejar la puerta al patio sin llave |
| Intrusión | Cuando alguien entra en un sistema sin permiso | Acceso no autorizado mediante la explotación de una falla. | Un hacker entrando a la base de datos de una tienda online. |
| Seguridad de red | Protocolos que defienden a cualquier infraestructura de ciberataques  | Uso de protocolos cifrados y barreras de tráfico | Usar un VPN  |

👉 Reglas:

- Máximo 3 líneas por celda
- Debe ser entendible para alguien sin experiencia

---

### 🔑 2. Permissions (accesos en sistemas)

Responder:

- ¿Qué significa:
    - Autenticación? Verificación de identidad.
    - Autorización? Verificación de permisos
- ¿Cuál es la diferencia entre ambas?
- Ejemplo developer:
    - Login → ¿qué es? Autenticación
    - Roles (admin/user) → ¿qué es? Autorización

👉 Relación con APIs y Sistemas: En las APIs, esto se maneja usualmente con Tokens (como JWT). El token le dice al servidor quién eres (Autenticación) y qué recursos puedes pedir (Autorización) en cada consulta.

---

### 🔒 3. A Good Password (lo mínimo obligatorio)

Responder:

- ¿Qué hace que una contraseña sea segura?
    - Larga, compleja y solo se use en un sitio especifico.
- ¿Por qué NO se deben guardar contraseñas en texto plano?
    - Porque si infiltran la base de datos, tendrían las contraseñas reales de todos.
- ¿Qué es hashing?
    - transformar la contraseña en una cadena de texto única e irrevesible por medio de un algoritmo. Eso se llamaba Hash.

👉 Ejemplo developer:

- ¿Cómo se manejan contraseñas en backend?
    - En el backend, nunca guardamos la contraseña. Guardamos el *hash*. Cuando el usuario intenta loguearse, "hasheamos" lo que escribió y comparamos si el resultado coincide con el hash guardado.

---

### ⚠️ 4. Vulnerabilities (fallas reales)

Responder:

- ¿Qué es una vulnerabilidad?
    - Es un error de diseño o programación que puede ser aprovechado
- Mencionar al menos 3 tipos comunes:
    - SQL Injection: El atacante envía código malicioso a través de un formulario para manipular la base de datos.
    - XSS: El atacante inyecta scripts (JS) en tu página para que se ejecuten en el navegador de otros usuarios y robar sus sesiones.
    - Exposición de datos: Dejar información sensible (como correos o IDs) visible en la URL o en respuestas de la API que no deberían enviarse.

👉 Ejemplo real:

- ¿Cómo una mala validación rompe una app?
    - Si un developer no valida que un campo de "Edad" solo reciba números, un atacante podría escribir código que borre toda la tabla de usuarios.

---

### 🚨 5. Intrusión (ataques)

Responder:

- ¿Qué es una intrusión?
    - El acto físico o digital de romper las barreras de seguridad para ganar control sobre un recurso.
- ¿Qué busca un atacante?
    - Generalmente tres cosas: Datos (venderlos), Dinero (extorsión/Ransomware) o Poder (usar tus servidores para otros ataques).
- ¿Qué pasa si una app es comprometida?
    - Pérdida de reputación, multas legales masivas, robo de propiedad intelectual y, en el peor de los casos, el cierre de la empresa.

👉 Ejemplo:

- Robo de datos
- Acceso no autorizado

---

### 🌐 6. Network Security (seguridad en red)

Responder:

- ¿Qué protege la seguridad de red?
    - La integridad y privacidad de los datos mientras viajan desde el dispositivo del usuario hasta el servidor
- ¿Qué es un firewall?
    - Un muro digital que analiza el tráfico y decide qué entra y qué sale de una red basado en reglas de seguridad.
- ¿Qué es HTTPS y por qué es importante?
    - Es la versión segura de HTTP. Cifra los datos para que, si alguien intercepta la señal (en un Wi-Fi público, por ejemplo), solo vea basura ilegible.

👉 Ejemplo developer:

- ¿Por qué usar HTTPS en APIs?
    - Al construir APIs, usar HTTPS es obligatorio para evitar ataques de "Hombre en el medio" (Man-in-the-Middle), donde alguien intercepta las claves API o tokens.

---

### 💻 7. Conexión directa con desarrollo (CLAVE)

Responder:

- ¿Qué errores comunes cometen los developers en seguridad?
- ¿Qué pasaría si:
    - No validas inputs? La base de datos puede ser borrada o secuestrada fácilmente.
    - No proteges rutas? Cualquier persona, con solo cambiar la URL (ej. `/admin`), podría entrar a funciones privadas
    - No usas HTTPS? Las contraseñas de tus usuarios viajarán visibles por internet para cualquier curioso.

---

### 🌍 8. Caso práctico real

Escenario:

> “Un usuario logra acceder a información que no le corresponde.”
> 

Responder:

- ¿Qué falló? La Autorización, el sistema no comprobó si ese usuario tenía permiso para ver la información de *otro* usuario.
- ¿Es problema de permisos, vulnerabilidad o intrusión?  Permisos
- ¿Cómo lo evitarías como developer?
    - Validar en el servidor que el usuario autenticado sea el dueño del recurso que intenta consultar.

---

### 🧪 9. Analogía obligatoria

Crear analogía:

| Concepto | Analogía |
| --- | --- |
| Permissions | Los roles y funciones que hacen posible la impresión de un libro: ej.  solo un escritor puede hacer el cambio definitivo. El editor solo revisa, no hace grandes cambios.  |
| Password | Llave de acceso a la caja del manuscrito. |
| Vulnerabilidad | Dejar el manuscrito en una caja sin llave o con cerrojo antiguo  |
| Intrusión | El robo del manuscrito.  |
| Seguridad de red | Las medidas para que, cuando el autor mande el manuscrito por correo al editor, nadie pueda interceptar