> [!TIP]  
> [Ver video](https://youtu.be/n1J7JTrzIZ4)

La capa de transporte es responsable de muchas de las funciones importantes para la disponibilidad de una red de computadoras. Estas incluyen **multiplexing** y **demultiplexing**, para manejar el tráfico, estableciendo conexiones de larga duración y asegurando la integridad de los datos a través del chequeo de errores y la verificación de los datos.

Al final de esta lección deberías describir qué es el multiplexing y demultiplexing, y cómo trabajan. Tendrás la capacidad de identificar la diferencia entre TCP y UDP, explicar el three-way handshake, y entender cómo los atributos de TCP son usados en este proceso. Finalmente, podrás describir de forma básica cómo los firewalls mantienen las redes seguras.

La capa de transporte tiene la capacidad de multiplex y demultiplex, lo cual ubica a esta capa aparte de las demás. **Multiplexing** en la capa de transporte significa que los nodos en la red tienen la habilidad de dirigir el tráfico hacia muchos diferentes servicios. **Demultiplexing** es el mismo concepto, solo que en el sentido opuesto, tomando todo el tráfico que está siendo dirigido hacia el nodo y entregándolo al servicio receptor apropiado.

La capa de transporte maneja el multiplexing y demultiplexing a través de puertos. Un puerto es un número de 16 bits que es usado para dirigir tráfico hacia servicios específicos que están ejecutándose en una computadora de la red.

¿Recuerdan el concepto de cliente y servidor? Un servidor o servicio es un programa ejecutándose en una computadora, esperando a responder requerimientos. Un cliente es otro programa que es quien requiere los datos. Diferentes servicios de la red se ejecutan mientras escuchan sobre puertos específicos para las solicitudes entrantes.

Por ejemplo, el puerto tradicional para HTTP o para el tráfico de la red descifrado es el puerto 80. Si nosotros queremos requerir una página web desde un servidor web ejecutándose en una computadora, escuchando sobre la IP 10.1.1.100, el tráfico sería dirigido hacia el puerto 80 en esa computadora. Los puertos son normalmente denotados con dos puntos después de la dirección IP. Así que la IP y puerto en este escenario pudieran ser descritos como `10.1.1.100:80`. Cuando son escritos de esta forma, es conocido como dirección de socket o número de socket.

El mismo dispositivo podría estar ejecutando un servidor FTP o protocolo de transferencia de archivos. FTP es un método viejo, usado para transferir archivos de una computadora a otra, pero aún muy usado. FTP tradicionalmente escucha en el puerto 21, así que si ustedes quieren establecer una conexión hacia un servidor FTP ejecutándose sobre la misma IP donde nuestro servidor web de ejemplo estaba ejecutándose, tienen que dirigir el tráfico hacia `10.1.1.100:21`.

Ustedes podrían estar trabajando como Soporte de TI en una pequeña empresa. En estos ambientes, un simple servidor puede alojar todas las aplicaciones necesarias para administrar un negocio. La misma computadora podría alojar un website, un servidor de correo para la compañía, servidor para compartir archivos, un servidor de impresión para compartir las impresoras de la red y muchas otras cosas. Todo esto es posible debido al multiplexing y demultiplexing, y el añadido de los puertos a nuestro esquema de direccionamiento.
