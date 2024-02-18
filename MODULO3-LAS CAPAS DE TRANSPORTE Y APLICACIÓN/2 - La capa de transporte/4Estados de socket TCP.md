> [!TIP]  
> [Ver video](https://youtu.be/rvlAyaniDus)

Un socket es la creación de instancias de un terminal en una conexión TCP potencial. Una creación de instancias es la implementación real de algo definido en otro lugar. Los sockets TCP requieren programas reales para poder crear sus instancias. Puedes comparar esto con un puerto que tiene una naturaleza más descriptiva y virtual. En otras palabras, puedes enviar tráfico al puerto que quieras, pero solo obtendrás una respuesta si un programa abrió un socket en ese puerto.

Puede haber sockets TCP en muchos estados. Y poder entender lo que significan te ayudará a solucionar problemas de conectividad de red como especialista de soporte de TI. Veremos los más comunes aquí.

- **LISTEN:** LISTEN significa que un socket TCP está disponible y escuchando las conexiones entrantes. Verías esto solo del lado del servidor.

- **SYN_SENT:** Esto significa que se ha enviado una solicitud de sincronización, pero la conexión no se estableció todavía. Verías esto solo del lado del cliente.

- **SYN_RECEIVED:** Esto significa que un socket, previamente en estado LISTEN, recibió una solicitud de sincronización y devolvió un SYN_ACK. Pero todavía no recibió el ACK final del cliente. Verías esto solo del lado del servidor.

- **ESTABLISHED:** Esto significa que la conexión TCP está en funcionamiento y que ambos lados son libres de enviarse datos. Verías este estado tanto del lado cliente como del lado servidor de la conexión. Esto será cierto para todos los siguientes estados de socket, además. Así que no lo olvides.

- **FIN_WAIT:** Esto significa que se envió un FIN, pero que el ACK correspondiente del otro lado todavía no se recibió.

- **CLOSE_WAIT:** Esto significa que la conexión se cerró en la capa TCP, pero que la aplicación que abrió el socket no lo liberó aún.

- **CLOSED:** Esto significa que la conexión finalizó por completo y que no es posible más comunicación.

Hay otros estados de socket TCP. Además, los estados de socket y sus nombres pueden variar de un sistema operativo a otro. Eso es porque existen fuera del alcance de la definición misma de TCP. TCP, como protocolo, es universal en su modo de uso, ya que todos los dispositivos que se comunican en el protocolo TCP tiene que hacerlo exactamente de la misma manera para que las comunicaciones sean exitosas. Elegir cómo describir los estados de un socket a nivel del sistema operativo no es tan universal. Al solucionar problemas en la capa TCP, asegúrate de verificar que las definiciones del estado de socket sean las exactas para los sistemas con los que trabajes.
