La resolución de nombres es una parte importante del funcionamiento de Internet. La mayor parte del tiempo, tu sistema operativo se encarga de todas las búsquedas por ti. Pero como especialista en soporte de TI, a veces puede ser útil ejecutar estas consultas para que puedas ver exactamente lo que ocurre detrás de escena.

Por suerte, hay muchas herramientas diferentes de línea de comandos por ahí que te ayudarán con esto. La herramienta más común se conoce como nslookup y está disponible en los tres sistemas operativos que estuvimos analizando, Linux, Mac y Windows.

El uso básico de nslookup es bastante simple. Ejecutas el comando nslookup con el nombre del host a continuación y la salida muestra qué servidor se utilizó para realizar la solicitud y su resolución. Supongamos que necesitabas saber la dirección IP de twitter.com. Con que escribieras `nslookup twitter.com` recibirías el registro A.

Nslookup es mucho más poderoso que eso. Incluye un modo interactivo que te permite establecer opciones adicionales y ejecutar muchas consultas consecutivas. Para iniciar una sesión nslookup interactiva, tan solo escribe nslookup, sin ningún nombre de host detrás. Deberías ver una comilla angular que funciona como puntero.

Desde el modo interactivo, puedes hacer muchas solicitudes consecutivas. También puedes realizar algo de configuración adicional que sirva como ayuda para una solución de problemas más detallada. Mientras estés en el modo interactivo, si escribes "server" y luego una dirección, se intentarán todas las siguientes consultas de resolución de nombres usando ese servidor en lugar del servidor de nombres predeterminado.

También puedes escribir "set type =" seguido de un tipo de registro de recursos. De manera predeterminada, nslookup devolverá registros A. Pero esto te permite pedir explícitamente registros Quad A o MX o incluso registros de texto asociados con el host.

Si de verdad quieres ver qué ocurre exactamente, puedes ingresar "set debug". Esto permitirá que la herramienta muestre los paquetes de respuesta completa, incluida cualquier solicitud de intermediarios y todos sus contenidos. Advertencia, esta es una gran cantidad de datos y puede contener detalles como el TTL restante, si es una respuesta en caché, hasta el número de serie del archivo de zona contra el cual se realizó la solicitud.
