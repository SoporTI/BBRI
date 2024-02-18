> [!TIP]  
> [Ver video](https://youtu.be/3k2U3tnhYX0)

En una red de área local, o LAN, los nodos pueden comunicarse entre sí
a través de sus direcciones MAC físicas. Esto funciona bien a pequeña escala
porque los conmutadores pueden aprender rápidamente las direcciones MAC conectadas a los puertos de los nodos
para reenviar las transmisiones adecuadamente.

Pero el direccionamiento MAC
no es un esquema que se escala bien, cada interfaz de red en el planeta
tiene una dirección MAC única y no están ordenadas de ninguna manera sistemática. No hay forma de saber en qué lugar del planeta
podría hallarse una dirección MAC en un momento dado, por lo que no es ideal
para comunicarse a la distancia.

Más adelante en esta lección, cuando presentemos ARP
o Protocolo de resolución de direcciones, verás que el modo en que los nodos aprenden
sobre el direccionamiento físico de cada uno no es traducible a nada
más allá de un solo segmento de red. Claramente necesitamos otra solución,
y esa es la capa de red y el Protocolo de internet o IP
en las direcciones IP que vienen con él.

Al final de esta lección,
podrás identificar una dirección IP, describir cómo se encapsulan los datagramas IP
dentro de la carga útil de una trama Ethernet y también identificar y describir correctamente
los diversos campos de un encabezado de datagrama IP.
