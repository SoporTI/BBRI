> [!TIP]  
> [Ver video](https://youtu.be/f_Mrh6lYX2g)

Las clases de direcciones fueron el primer intento de dividir el espacio IP global de Internet. La división en subredes se introdujo cuando fue evidente que las clases de direcciones en sí mismas no eran tan eficientes para mantener todo organizado. Pero a medida que Internet siguió creciendo, la división tradicional en subredes no pudo seguir el ritmo.

Con las subredes tradicionales y las clases de dirección, la ID de la red siempre es de 8 bits para redes de clase A, 16 bits para redes de clase B, o 24 bits para redes de clase C. Esto significa que solo podría haber 254 redes de clase C, pero también significa que hay 2,970,152 redes de clase C potenciales. Son muchísimas entradas en una tabla de enrutamiento.

Para colmo, el tamaño de estas redes no siempre es apropiado para las necesidades de la mayoría de las empresas. 254 hosts en una red de clase C son demasiado pocos para muchos casos de uso, pero los 65,534 hosts disponibles en una red de clase B a menudo son demasiados. Muchas compañías terminaron con varias redes de clase C contiguas para satisfacer sus necesidades. Eso implicó que las tablas de enrutamiento terminaran con un montón de entradas para un grupo de redes de clase C que, en realidad, se enrutaban al mismo lugar.

Aquí es donde entra en juego CIDR, o enrutamiento entre dominios sin clase. CIDR es un enfoque aún más flexible para describir bloques de direcciones IP. Expande el concepto de división en subredes: usa máscaras de subred para demarcar redes. Demarcar algo significa poner de relieve algo. Al hablar de redes de computadoras, a menudo oirás el término "punto de demarcación" para describir dónde termina una red o sistema y comienza otro.

En nuestro modelo anterior, confiamos en una ID de red, una ID de subred y una ID de host para entregar un datagrama IP a la ubicación correcta. Con CIDR, la ID de red y la ID de subred se combinan en una sola. Con CIDR obtenemos esta notación de barra abreviada que analizamos en el video anterior sobre la división en subredes. Esta notación de barra también se conoce como notación CIDR.

CIDR básicamente abandona por completo el concepto de clases de dirección, lo que permite que una dirección se defina con solo dos ID individuales. Tomemos 9.100.100.100 con una máscara de red 255.255.255.0. Recuerda, esto también puede escribirse como 9.100.100.100/24. En un mundo donde ya no nos importa la clase de direcciones de esta IP, todo lo que necesitamos es lo que la máscara de red nos diga para determinar la ID de la red. En este caso, eso sería 9.100.100, la ID de host sigue siendo la misma.

Esta práctica no solo simplifica cómo los routers y otros dispositivos de red deben pensar en partes de una dirección IP, sino también permite tamaños de red más arbitrarios. Antes, los tamaños de red eran estáticos. Piensa solo en clase A, clase B o clase C, y solo las subredes podían ser de diferentes tamaños.

CIDR permite que las propias redes tengan diferentes tamaños. Antes, si una empresa necesitaba más direcciones de las que una sola clase C podría proporcionarle, necesitaba una segunda clase completa C. Con CIDR, podrían combinar ese espacio de direcciones en una porción contigua con una máscara de red de /23 o 255.255.254.0. Esto significa que los routers ahora solo necesitan conocer una entrada en su tabla de enrutamiento, en lugar de dos, para entregar tráfico a estas direcciones.

También es importante destacar que obtienes ID de host adicionales disponibles con esta práctica. Recuerda que siempre pierdes dos ID de host por red. Por lo tanto, si una red /24 tiene 2 a la octava (2Λ8) o 256 hosts potenciales, en realidad solo tienes 256 - 2, o 254 IP disponibles para asignar. Si necesitas dos redes de este tamaño, tienes un total de 254 + 254, o 508 hosts. Una sola red única /23, en cambio, es dos a la novena (2Λ9) o 512. 512 - 2, 510 hosts.

Tómate un segundo y guárdalo en tu memoria. Entonces, cuando estés listo, tenemos una breve evaluación sin calificación para ti antes de pasar a la próxima lección: enrutamiento.
