> [!TIP]  
> [Ver video](https://youtu.be/CLupiGxEdWM)

Con ping, ahora tienes una manera de determinar si puedes llegar a una cierta computadora desde otra. También puedes comprender la calidad general de la conexión. Pero las comunicaciones a través de redes, en especial a través de Internet, por lo general cruzan muchísimos nodos intermediarios. A veces, necesitas una manera de determinar en qué parte de la larga cadena de saltos de router están en verdad los problemas. Traceroute al rescate.

Traceroute es una utilidad impresionante que te permite descubrir las rutas entre dos nodos y te brinda información sobre cada salto en el camino. Traceroute funciona a través de una técnica de manipulación inteligente del campo TTL a nivel de IP. Anteriormente aprendimos que el valor del campo TTL se reduce de a una unidad por cada router que reenvía el paquete. Cuando el campo TTL llega a cero, el paquete se desecha y se envía un mensaje ICMP "Time Exceeded" (tiempo excedido) al servidor de origen.

Traceroute usa el campo TTL configurándolo primero en 1 para el primer paquete, luego 2 para el segundo, 3 para el tercero y así sucesivamente. Mediante esta pequeña acción inteligente, traceroute se asegura de que el primer paquete enviado será descartado por el primer salto del router. Esto resulta en un mensaje ICMP de tiempo excedido. El segundo paquete llegará al segundo router, el tercer paquete llegará al tercero, y así sucesivamente. Esto continúa hasta que el paquete finalmente llega a destino.

Para cada salto, traceroute enviará tres paquetes idénticos. Al igual que con ping, la salida de un comando traceroute es bastante simple. En cada línea, verás el número del salto y el tiempo de ida y vuelta para los tres paquetes. También verás la IP del dispositivo en cada salto y un nombre de host si traceroute puede resolverlo.

En Linux y MacOS, traceroute envía paquetes UDP a puertos con números muy altos. En Windows, el comando tiene un nombre abreviado, tracert, y de manera predeterminada usa la solicitud de eco ICMP. En todas las plataformas, traceroute tiene más opciones de las que se pueden especificar usando las marcas de línea de comando.

Dos herramientas más que son similares a traceroute son mtr en Linux y MacOS y pathping en Windows. Estas dos herramientas actúan como traceroutes de larga duración para que puedas ver mejor cómo cambian las cosas durante un período de tiempo. Mtr trabaja en tiempo real y actualizará continuamente su salida con todos los datos actuales en conjunto sobre el traceroute. Puedes comparar esto con el pathping, que se ejecuta durante 50 segundos y luego muestra los datos finales en conjunto a la vez.
