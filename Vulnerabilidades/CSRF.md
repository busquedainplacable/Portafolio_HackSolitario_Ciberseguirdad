# 🕵️ Vulnerabilidad: CSRF (Cross-Site Request Forgery)

## 📝 Descripción
Este documento forma parte de mi portafolio técnico como **HackSolitario**, donde demuestro la explotación práctica de la vulnerabilidad CSRF en un entorno controlado. Cada evidencia representa un paso real, ejecutado y validado, que refleja mi compromiso con la ciberseguridad profesional y mi disciplina en la documentación técnica. La vulnerabilidad CSRF ocurre cuando un atacante logra que un usuario autenticado ejecute acciones no deseadas en una aplicación web, aprovechando la falta de validación en las solicitudes. Este caso práctico muestra cómo se puede manipular un formulario vulnerable para forzar acciones como el cambio de contraseña sin el consentimiento del usuario.

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

### 1. Despliegue del entorno de laboratorio
![IP del laboratorio](Evidencias/laboratorio_jp_dockerlabs.png)

### 2. Registro de usuario en la aplicación vulnerable
![Registro de usuario](Evidencias/REGISTRO_USR.png)

### 3. Inicio de sesión en el laboratorio
![Inicio de sesión](Evidencias/INICIO_SESIÓN.png)

### 4. Usuario autenticado dentro del laboratorio
![Sesión activa](Evidencias/registrado_dentro_del_laboratorio_csrf.png)

### 5. Interceptación de solicitudes en Burp Suite
![Interceptación en Burp Suite](Evidencias/burpsuite_interceptando_solicitudes.png)

### 6. Solicitud de cambio de contraseña interceptada
![Cambio de contraseña interceptado](Evidencias/csrf_cambio_contraseña_interceptado.png)

### 7. Código fuente del payload en Visual Studio Code
![Código fuente en VSC](Evidencias/csrf_codigo_vrc.png)

### 8. Payload malicioso en HTML
![Payload CSRF en HTML](Evidencias/csrf_payload_html.png)

### 9. Entorno HTML ejecutando el payload
![Entorno HTML ejecutado](Evidencias/csrf_entorno_html_ejecutado.png)

### 10. Prueba manual del payload en Burp Suite (Repeater)
![Repeater en Burp Suite](Evidencias/csrf_repeater_burpsuite.png)

### 11. Vista general del laboratorio en ejecución
![Laboratorio en ejecución](Evidencias/IMG_LABORATORIO.png)

### 12. Confirmación de éxito en la explotación
![Laboratorio CSRF completado](Evidencias/csrf_laboratorio_completado.png)
  
  ```html
  <form action="http://172.17.0.2/change-password" method="POST">
    <input  name="new_password" value="hacker">
  </form>

_____________________________________________________________________________________________________________________________________

## 🧠 Conclusión

La vulnerabilidad CSRF fue explotada con éxito en un entorno de laboratorio.  
Se logró demostrar cómo un atacante puede manipular solicitudes legítimas y ejecutar acciones críticas en nombre de un usuario autenticado.  

Este ejercicio refuerza la importancia de implementar medidas de seguridad como:
- Tokens CSRF únicos por sesión.
- Validación estricta de las solicitudes.
- Buenas prácticas de desarrollo seguro.

Con esta documentación, dejo evidencia clara de mi capacidad para identificar, explotar y registrar vulnerabilidades de manera profesional, consolidando mi portafolio como HackSolitario y mi evolución constante en el campo de la ciberseguridad.

_______________________________________________________________________________________________________________________________________

## 🧠 Reflexión personal

Este reto me permitió comprender a fondo cómo una vulnerabilidad aparentemente sencilla como CSRF puede tener un impacto crítico si no se implementan medidas de protección como tokens únicos.  
Lo más desafiante fue interceptar correctamente la solicitud de cambio de contraseña y construir un payload funcional que se ejecutara sin interacción del usuario.

Aprendí a documentar cada paso con precisión, a validar visualmente cada evidencia, y a mantener una narrativa clara para que otros puedan replicar el proceso.  
Este ejercicio fortaleció mi disciplina técnica y mi capacidad para comunicar lo que hago, no solo ejecutarlo.

Como HackSolitario, cada vulnerabilidad que documento representa una batalla ganada en mi camino hacia la excelencia profesional.


