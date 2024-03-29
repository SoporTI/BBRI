> [!TIP]  
> [Ver video](https://youtu.be/sJyb5hh5aOU)

¡Felicitaciones! Ahora entiendes cómo se utilizan ambas direcciones MAC en el Linklayer de datos y cómo se utilizan las direcciones IP en la capa de red. Ahora necesitamos aclarar cómo estos dos tipos de direcciones separadas se relacionan entre sí. Aquí es donde entra en juego el protocolo de resolución de direcciones o ARP.

ARP es un protocolo utilizado para descubrir la dirección de hardware de un nodo con una dirección IP determinada. Una vez que un datagrama IP se ha formado completamente necesita ser encapsulado dentro de una trama Ethernet. Esto significa que el dispositivo transmisor necesita una dirección MAC de destino para completar el encabezado de la trama Ethernet.

Casi todos los dispositivos conectados a la red conservan la tabla ARP local. La tabla ARP es solo una lista de direcciones IP y las direcciones MAC asociadas con ellas. Digamos que queremos enviar algunos datos a la dirección IP 10.20.30.40. Puede ocurrir que este destino no tenga una entrada en la tabla ARP. Cuando esto sucede, el nodo que quiere enviar datos envía un mensaje de difusión ARP a la dirección de transmisión MAC que son todos los EFH. Este tipo de mensajes de difusión ARP son entregados a todas las computadoras de la red local.

Una vez la interfaz de red a la que se le ha asignado la IP 10.20.30.40 recibe esta transmisión ARP, esta envía lo que se conoce como una respuesta ARP. Este mensaje de respuesta contendrá la dirección MAC para la interfaz de red en cuestión. Ahora la computadora transmisora sabe qué dirección MAC poner en el campo de dirección de hardware de destino y así la trama Ethernet está lista para la entrega. También es probable que almacene esta dirección IP en su tabla ARP local para que no tenga que enviar una transmisión ARP la próxima vez que necesite comunicarse con esta IP. Práctico.

Las entradas de la tabla ARP generalmente caducan después de un corto período de tiempo para garantizar que los cambios en la red se tengan en cuenta. Así que no esperes que permanezcan de la forma en que espero que permanezcas con nosotros para el próximo cuestionario sin calificación.
