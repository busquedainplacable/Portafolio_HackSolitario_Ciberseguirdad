# 🕵️ Vulnerabilidad: CSRF (Cross-Site Request Forgery)

## 📝 Descripción
CSRF ocurre cuando un atacante logra que un usuario autenticado ejecute acciones no deseadas en una aplicación web, aprovechando la falta de validación en las solicitudes.

## 🎯 Objetivo del reto
- Forzar al usuario autenticado a realizar una acción sin su consentimiento (ejemplo: cambiar contraseña, transferir fondos, modificar datos).

## 🛠️ Pasos ejecutados
1. Identificación de un formulario vulnerable sin token CSRF.
2. Creación de una petición maliciosa que replica la acción legítima.
3. Inserción del payload en un entorno controlado (ejemplo: HTML externo).
4. Ejecución de la acción cuando la víctima visita el enlace.

## 🔧 Herramientas utilizadas
- Burp Suite (para interceptar y modificar solicitudes).
- Navegador con extensiones de prueba.
- Editor de texto para construir el payload.

## 📂 Evidencias
- Capturas de pantalla del formulario vulnerable.
- Ejemplo del payload usado:  
  ```html
  <form action="http://victima.com/change-password" method="POST">
    <input type="hidden" name="password" value="123456">
    <input type="submit" value="Enviar">
  </form>
