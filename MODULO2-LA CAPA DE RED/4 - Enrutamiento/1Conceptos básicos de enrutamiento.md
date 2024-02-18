> [!TIP]  
> [Ver video](https://youtu.be/K86nKnjvMaM)

Internet es un logro tecnológico increíble, impresionante. Une millones de redes individuales y permite que las comunicaciones fluyan entre ellas. Desde casi cualquier lugar del mundo, ahora puedes acceder a datos ubicados en otro lugar. A menudo, en tan solo fracciones de segundo.

La forma en que ocurren las comunicaciones a través de todas estas redes, lo que te permite acceder a los datos del otro lado del planeta, es a través del enrutamiento. Al final de esta lección, podrás describir los conceptos básicos del enrutamiento y cómo funcionan las tablas de enrutamiento. Podrás identificar algunos de los principales protocolos de enrutamiento y lo que hacen, además de identificar un espacio de direcciones no enrutable y su uso. También comprenderás el sistema RFC y cómo hizo de Internet lo que es hoy.

Todas estas son habilidades muy importantes para solucionar los problemas de red que puedes encontrarte como especialista en soporte de TI. El enrutamiento es una de esas cosas que es muy simple y, a la vez, muy compleja. A un nivel muy alto, qué es el enrutamiento y cómo funcionan los routers en realidad es bastante simple. Pero bajo el capó, el enrutamiento es un tema muy complejo y tecnológicamente avanzado. Se han escrito libros enteros sobre el tema.

Hoy en día, los problemas de enrutamiento más profundos son manejados casi en exclusiva por los ISP y solo las empresas más grandes. Te ofreceremos la visión general básica del enrutamiento para darte una formación completa sobre redes, ya que es un tema importante para comprender, pase lo que pase. Pero de ninguna manera lo veremos a fondo.

Desde un punto de vista muy básico, un router es un dispositivo de red que reenvía el tráfico según la dirección de destino de ese tráfico. Un router es un dispositivo que tiene, al menos, dos interfaces de red, ya que tiene que estar conectado a dos redes para hacer su trabajo.

El enrutamiento básico tiene unos pocos pasos. Uno, un router recibe un paquete de datos en una de sus interfaces. Dos, el router examina la IP de destino de este paquete. Tres, el router busca la red de destino de esta IP en su tabla de enrutamiento. Cuatro, el router reenvía el paquete a través de la interfaz más cercana a la red remota, según lo determinado por la información adicional en la tabla de enrutamiento. Estos pasos se repiten tantas veces como sea necesario hasta que el tráfico llegue a su destino.

Imaginemos un router conectado a dos redes. Llamaremos a la primera red "red A" y le daremos el espacio de direcciones 192.168.1.0/24. Llamaremos a la segunda red "red B" y le daremos el espacio de direcciones 10.0.0.0/24. El router tiene una interfaz en cada red. En la red A, su IP es 192.168.1.1 y en la red B, su IP es 10.0.0.254. Recuerda, las direcciones IP corresponden a las redes, no a los nodos individuales en una red.

Una computadora en la red A, cuya dirección IP es 192.168.1.100, envía un paquete a la dirección 10.0.0.10. Esta computadora sabe que 10.0.0.10 no está en su subred local. Así que envía este paquete a la dirección MAC de su puerta de enlace, el router. La interfaz del router en la red A recibe el paquete porque ve que la dirección MAC de ese destino le pertenece.

Luego, el router quita la encapsulación de la capa de enlace de datos, y se queda con el contenido de la capa de red, el datagrama IP. Ahora, el router puede inspeccionar directamente el encabezado del datagrama IP para el campo IP de destino. Encuentra la IP de destino 10.0.0.10. El router mira su tabla de enrutamiento y ve que la red B, o red 10.0.0.0/24, es la red correcta para la IP de destino. También ve que esta red está a solo un salto de distancia. De hecho, ya que está directamente conectado, el router incluso tiene la dirección MAC para esta IP en su tabla ARC.

A continuación, el router debe formar un nuevo paquete para reenviar a la red B. Toma todos los datos del primer datagrama IP y los duplica. Pero reduce el valor del campo TTL en uno y calcula una nueva suma de verificación. Luego, encapsula este nuevo datagrama IP dentro de una nueva trama de Ethernet. Esta vez, configura su propia dirección MAC de la interfaz en la red B como la dirección MAC de origen. Como tiene la dirección MAC 10.0.0.10 en su tabla ARC, la establece como dirección MAC de destino.

Por último, el paquete se envía desde su interfaz en la red B y los datos finalmente se entregan al nodo ubicado en 10.0.0.10. Ese es un ejemplo bastante básico de cómo funciona el enrutamiento, pero vamos a hacerlo un poco más complicado: vamos a introducir una tercera red. Todo lo demás sigue siendo lo mismo.

Tenemos la red A, cuyo espacio de direcciones es 192.168.1.0/24. Tenemos la red B, cuyo espacio de direcciones es 10.0.0/24. El router que une a estas dos redes todavía tiene las IP 192.168.1.1 en la red A y 10.0.0.254 en la red B. Pero vamos a introducir una tercera red, la red C. Su espacio de direcciones es 172.16.1.0/23.

Hay un segundo router que conecta las redes B y C. Tiene una interfaz en la red B, cuya IP es 10.0.0.1, y una interfaz en la red C, cuya IP es 172.16.1.1. En esta ocasión, nuestra computadora en 192.168.1.100 quiere enviar algunos datos a la computadora cuya IP es 172.16.1.100.

Vamos a omitir las cosas de la capa de enlace de datos, pero recuerda que eso sigue ocurriendo, por supuesto. La computadora en 192.168.1.100 sabe que 172.16.1.100 no está en su red local, por lo que envía un paquete a su puerta de enlace, el router entre la red A y la red B.

Nuevamente, el router inspecciona el contenido de este paquete. Ve una dirección de destino 172.16.1.100 y a través de una búsqueda en su tabla de enrutamiento, sabe que el camino más rápido para llegar a la red 172.16.1.0/23 es a través de otro router con una IP de 10.0.0.1. El router disminuye el campo TTL en una unidad y lo envía al router en 10.0.0.1.

Este router luego repasa los movimientos, sabe que la IP de destino 172.16.1.100 está directamente conectada y reenvía el paquete a su destino final.

Esos son los fundamentos del enrutamiento. La única diferencia entre nuestros ejemplos y cómo funcionan las cosas en Internet es la escala. Los routers suelen estar conectados a mucho más que apenas dos redes. Muy a menudo, tu tráfico puede tener que cruzar una docena de routers antes de llegar a su destino final. Y por último, con el fin de proteger contra las interrupciones, los routers centrales de Internet están típicamente conectados en una malla, lo que implica que puede haber muchos caminos diferentes para que un paquete tome. Aun así, los conceptos son todos los mismos. Los routers inspeccionan la IP de destino, miran la tabla de enrutamiento para determinar el camino más rápido y reenvían el paquete por ese camino. Esto sucede una y otra vez. Cada paquete que forma cada pedacito de tráfico en todo Internet, en todo momento. Genial, ¿no?
