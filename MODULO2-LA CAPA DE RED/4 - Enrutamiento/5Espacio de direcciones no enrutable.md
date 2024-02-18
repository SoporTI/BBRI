> [!TIP]  
> [Ver video](https://youtu.be/rI5dOX2HSck)

# Breve Lección de Historia

Incluso en 1996, era obvio que Internet estaba creciendo a un ritmo que no podría mantenerse. Cuando el protocolo IP se definió por primera vez, definió una dirección IP como un solo número de 32 bits. Un solo número de 32 bits puede representar 4,294,967,295 números únicos, lo que definitivamente suena como mucho, pero a partir de 2017, la población estimada en el planeta es de 7,500 millones de habitantes. Esto significa que el estándar IPv4 ni siquiera tiene suficientes direcciones IP disponibles para cada persona en el planeta. También puede dar cuenta de centros de datos completos con miles y miles de computadoras necesarios para que las empresas de tecnología a gran escala funcionen.

Así, en 1996, se publicó el documento **RFC 1918**. RFC significa "solicitud de comentarios" y tiene un largo historial de acuerdos de requisitos normativos para mantener Internet en funcionamiento entre los responsables de que ello suceda. RFC 1918 esbozó una serie de redes que se definirían como espacio de direcciones no enrutables.

El espacio de direcciones no enrutables es básicamente lo que parece. Son rangos de IP que cualquier persona puede usar, a los que no se les puede enrutar tráfico. No todas las computadoras conectadas a Internet necesitan poder comunicarse con cualquier otra computadora conectada a Internet. El espacio de direcciones no enrutables permite que los nodos en dicha red se comuniquen entre sí, pero ningún router de puerta de enlace podrá intentar reenviar el tráfico a este tipo de red.

Esto puede sonar increíblemente limitante y, en cierta forma, lo es. En un futuro módulo, veremos una tecnología conocida como **NAT** o traducción de direcciones de red. Permite que las computadoras en espacios de direcciones no enrutables se comuniquen con otros dispositivos en Internet. Pero por ahora, vamos a analizar el espacio de direcciones no enrutables sin nada más.

RFC 1918 definió tres rangos de direcciones IP a las que ningún router les enviará tráfico. Eso significa que no pertenecen a nadie y que cualquiera puede usarlas. De hecho, como están separados de la forma en que el tráfico se mueve a través de Internet, no hay límite para la cantidad de personas que pueden usar estas direcciones para sus redes internas.

Los tres rangos principales del espacio de direcciones no enrutables son **10.0.0.0/8**, **172.16.0.0/12** y **192.168.0.0/16**. Cualquiera puede usar estos rangos libremente en sus redes internas. Debe señalarse que los protocolos de puerta de enlace interior enrutarán tráfico a estos espacios de direcciones. Por lo tanto, es apropiado usarlos dentro de un sistema autónomo, pero los protocolos de puerta de enlace exterior no los usarán.

Vimos mucho material en este módulo. Felicitaciones por seguir adelante. A continuación, hablaremos de las capas de transporte y aplicación. Pero primero, otro cuestionario. Puedes hacerlo. Y recuerda, siempre puedes regresar y revisar el material tanto como lo necesites.
