> [!TIP]  
> [Ver video](https://youtu.be/PK_hNWXZl_8)

Simplemente no es posible que Internet en su totalidad y que todas las redes conectadas cambien a IPv6 a la vez. Habría demasiada coordinación en juego. Demasiados dispositivos antiguos que hasta podrían no saber comunicarse en IPv6 en absoluto seguirían requiriendo conexiones. Así que la única manera en que IPv6 quede establecida es desarrollar una forma en la que el tráfico de IPv6 y de IPv4 coexistan. Esto permitiría a las organizaciones individuales hacer la transición cuando puedan.

Un ejemplo de cómo esto puede funcionar es lo que se conoce como espacio de direcciones mapeadas IPv4. Las especificaciones de IPv6 tienen una cantidad de direcciones reservadas que pueden correlacionarse directamente a una dirección IPv4. Cualquier dirección IPv6 que comience con 80 ceros y luego siga con 16 unos, se entiende como parte del espacio de direcciones mapeadas de IPv4. Los 32 bits restantes de la dirección IPv6 son los mismos 32 bits de la dirección IPv4 que debe representar. Esto nos da una vía para que el tráfico IPv4 se mueva a través de una red IPv6. Pero, probablemente, más importante es que el tráfico IPv6 tenga una manera de moverse a través de redes IPv4. Le es más fácil hacer el cambio a IPv6 a una organización individual que a las redes en el corazón de Internet.

Entonces, mientras la adopción de IPv6 se generalice cada vez más, necesitará una manera de moverse sobre los viejos restos de IPv4 de la red troncal de Internet. La principal forma de lograrlo hoy es a través de túneles IPv6.

Los túneles IPv6 son bastante simples conceptualmente. Constan de servidores de túneles IPv6 en cualquier extremo de una conexión. Estos servidores de túneles IPv6 toman el tráfico IPv6 entrante y lo encapsulan en datagramas IPv4 tradicionales. Luego, esto se entrega por el espacio de Internet IPv4, donde otro servidor de túnel IPv6 lo recibe. Ese servidor lleva a cabo la desencapsulación y difunde el tráfico IPv6 más allá en la red.

Junto con las tecnologías de túnel IPv6, también ha surgido el concepto de proveedores de túneles IPv6. Son empresas que te proveen terminales de túneles IPv6 para que no tengas que incorporar equipos adicionales a tu red. Hay muchos protocolos en competencia para que estos tipos de túneles IPv6 usen. Dado que esto todavía es un espacio nuevo y en evolución, no está claro quién será el ganador. Te dejé algunos vínculos para que leas sobre los principales competidores, justo después de este video.

En realidad, no importa qué tecnología de túneles termina convirtiéndose en la solución más común. Probablemente se desvanecerá con el tiempo. El futuro de las redes es la adopción de IPv6 como protocolo principal en la capa de red, y un día ya no necesitaremos más túneles. El futuro no tiene límites ni túneles, o algo por el estilo.

Has hecho un trabajo increíble con toda esta información. Tómate un tiempo para felicitarte. Tienes un cuestionario final y un proyecto final que aprobar. Y luego puedes quitar este curso de tu lista de tareas pendientes. ¿Comienzas a ver la luz al final del túnel?
