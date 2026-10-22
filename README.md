### Respuestas sobre el comportamiento del formulario

#### 1. ¿Cómo se ven los espacios, las tildes y la arroba?
Los caracteres especiales que no pertenecen al estándar ASCII (como espacios, tildes y la arroba) se transforman mediante un proceso llamado **codificación URL** (o *URL encoding*):
* **La arroba (`@`):** Se convierte en el código `%40` (como se observa en tu correo: `faj%40af`).
* **Los espacios:** Dependiendo del navegador o la configuración, se transforman en un signo de más (`+`) o en el código `%20`.
* **Las tildes y la 'ñ':** Se convierten en secuencias de bytes precedidas por signos de porcentaje (por ejemplo, la `á` se convierte en `%C3%A1`).

#### 2. ¿Qué pasa con los campos que no llenaste?
Si dejas un campo vacío pero este tiene un atributo `name` asignado en el HTML, el formulario **se envía de todas formas**, mostrando la clave pero sin ningún valor. En la barra de direcciones verás el nombre del campo seguido de un signo igual vacío (por ejemplo: `&campo_vacio=`). Si el campo no tiene un atributo `name`, directamente se ignora y no aparece en la URL.

#### 3. ¿Por qué un formulario con contraseñas nunca debería usar method="get"?
Nunca se debe usar el método `GET` para enviar contraseñas o datos sensibles por tres razones críticas de seguridad:
1. **Visibilidad total:** Los datos viajan expuestos en texto plano directamente en la barra de direcciones (URL).
2. **Historial del navegador:** La contraseña queda guardada de forma permanente en el historial de navegación de la computadora del usuario.
3. **Registros del servidor (Logs):** Las URLs solicitadas se almacenan automáticamente en los archivos de registro del servidor web, exponiendo las credenciales a cualquier administrador o atacante que acceda al servidor. 

*Para manejar datos sensibles, siempre se debe utilizar el método **`POST`**, el cual envía la información oculta dentro del cuerpo de la petición HTTP.*
