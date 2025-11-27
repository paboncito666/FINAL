Rate-limit

Qué es:
Es una técnica que limita cuántas veces un usuario o sistema puede hacer una acción en un determinado período de tiempo (por ejemplo, 100 peticiones por minuto).

Para qué sirve:
Para evitar abusos, proteger servicios de ataques (como DoS o intentos de fuerza bruta), y mantener el buen rendimiento del servidor.

Ejemplo real:
Tu API de inicio de sesión permite solo 5 intentos de contraseña por minuto por usuario. Si alguien intenta más, se bloquea temporalmente para evitar ataques de fuerza bruta.

CORS (Cross-Origin Resource Sharing)

Qué es / Qué problema resuelve:
Es un mecanismo de seguridad de los navegadores que controla qué páginas web pueden hacer peticiones a un servidor que está en otro dominio.
Sin CORS, una web maliciosa podría hacer peticiones en tu nombre a otros servicios sin que lo notes.

Ejemplo real:
Tienes un frontend en https://miapp.com y un backend en https://api.miapp.com.
Sin CORS, el navegador bloquearía las peticiones del frontend al backend. Configuras CORS para permitir que ese dominio autorizado (miapp.com) acceda.

JWT (JSON Web Token)

Qué es un token:
Es un “pase” digital que el cliente envía al servidor para demostrar que está autenticado o autorizado, sin tener que enviar el usuario y la contraseña cada vez.

Qué lleva dentro:
Un JWT contiene tres partes:

Header: tipo de token y algoritmo de firma

Payload: información (claims) como userId, roles, fecha de expiración

Firma (signature): garantiza que el token no fue modificado

Todo va codificado en Base64 y firmado.

Para qué se usa:
Para autenticación sin estado (“stateless”): el servidor no necesita guardar sesiones.
Cada vez que el cliente hace una petición, manda el JWT y el servidor solo verifica la firma.

Ejemplo real:
Un usuario inicia sesión en tu aplicación. El servidor genera un JWT con su id y roles, y lo devuelve al navegador. El frontend lo guarda (p. ej., en localStorage) y lo envía en cada petición como Authorization: Bearer <token>.