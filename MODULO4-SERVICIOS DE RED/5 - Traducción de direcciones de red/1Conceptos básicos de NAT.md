> [!TIP]  
> [Ver video](https://youtu.be/cfVJYs9jXE4)

# Traducción de Direcciones de Red (NAT)

Hola de nuevo. ¿Todo listo para meternos de lleno en esto? A diferencia de los protocolos como DNS y DHCP, la traducción de direcciones de red, o NAT, es más una técnica que un estándar definido. Esto significa que algo de lo que analizaremos en esta lección puede tener un nivel superior que algunos de nuestros otros temas. Diferentes sistemas operativos y diferentes proveedores de hardware de red han implementado los detalles de NAT de diferentes maneras. Pero los conceptos de lo que logra son bastante constantes.

La traducción de direcciones de red hace más o menos lo que parece. Toma una dirección IP y la traduce en otra. Hay muchas razones por las que querríamos hacer esto. Van desde salvaguardas de seguridad a preservar las cantidades limitadas de espacio disponible de IPV4. Vamos a discutir las implicaciones de NAT y la IP antes del espacio de direcciones más adelante en esta lección. Pero por ahora vamos a concentrarnos en cómo funciona NAT en sí y cómo puede proporcionar medidas de seguridad adicionales a una red.

En su nivel más básico, NAT es una tecnología que permite que una puerta de enlace, por lo general un router o un firewall, reescriban la IP de origen de un datagrama IP saliente al tiempo que mantienen la IP original para reescribirla en la respuesta. Para explicar esto mejor, veamos un ejemplo simple de NAT.

Supongamos que tenemos dos redes, la red A consiste en el espacio de direcciones 10.1.1.0/24 y la red B consiste en el espacio de direcciones 192.168.1.0/24. Entre estas redes hay un router que tiene una interfaz en la red A cuya IP es 10.1.1.1 y una interfaz en la red B cuya IP es 192.168.1.1. Ahora pongamos dos computadoras en estas redes. La computadora 1 está en la red A, y tiene una IP de 10.1.1.100; la computadora 2 está en la red B y tiene una IP de 192.168.1.100.

La computadora 1 quiere comunicarse con un servidor web en la computadora 2. Entonces crea el paquete apropiado en todas las capas y lo envía a su puerta de enlace principal: el router ubicado entre las dos redes. Hasta aquí, esto es muy parecido a muchos de nuestros ejemplos anteriores, pero en este caso, el router está configurado para realizar NAT para cualquier paquete saliente.

Normalmente, un router inspeccionará el contenido de un datagrama IP, disminuirá el TTL en 1, recalculará la suma de verificación y reenviará el resto de los datos en la capa de red sin tocarlos. Pero con NAT, el router también reescribirá la dirección IP de origen, que en este caso se convierte en la IP del router en la red B o 192.168. 1.1.

Cuando el datagrama llega a la computadora 2, parecerá que se originó en el router, no en la computadora 1. Ahora la computadora 2 elabora su respuesta y la envía de regreso al router. El router, a sabiendas de que este tráfico está realmente destinado a la computadora 1, reescribe el campo IP de destino antes de reenviarlo.

Lo que hace NAT en este ejemplo es ocultarle a la computadora 2 la IP de la computadora 1. Esto se conoce como enmascaramiento de IP. El enmascaramiento de IP es un importante concepto de seguridad. El concepto más básico en juego aquí es que nadie puede establecer una conexión con tu computadora si no sabe qué dirección IP tiene. Al usar NAT en la forma que acabamos de describir, de hecho, podríamos tener cientos de computadoras en la red A, con todas sus direcciones IP traducidas por el router a su propia IP. Para el mundo exterior, todo el espacio de direcciones de la red A está protegido y es invisible. Esto se conoce como "NAT uno a muchos", y lo verás en uso en muchas LAN en la actualidad.
