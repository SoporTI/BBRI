Ahora que conoces los fundamentos de cómo funciona cada capa de nuestro modelo de red, hagamos un ejercicio para ver cómo funciona todo en cada paso del camino. Alerta de spoiler: vamos a hablar un poco como cerebritos, en un buen sentido.

Imagina tres redes. La red A va a contener el espacio de direcciones 10.1.1.0/24. La red B va a contener el espacio de direcciones 192.168.1.0/24, y la red C será 172.16.1.0/24.

El router A se encuentra entre la red A y la red B con una interfaz cuya IP está configurada como 10.1.1.1 en la red A, y una interfaz en 192.168.1.254 en la red B.

Hay un segundo router, el router B, que conecta las redes B y C. Tiene una interfaz en la red B, cuya dirección IP es 192.168.1.1, y una interfaz en la red C, cuya dirección IP es 172.16.1.1.

Ahora vamos a poner una computadora en una de las redes. Imagina que es un equipo de escritorio, ubicado en el escritorio de alguien en el lugar de trabajo. Será nuestro cliente en esta situación y la llamaremos computadora 1. Es parte de la red A y se le asignó la dirección IP 10.1.1.100.

Ahora, pongamos otra computadora en una de las otras redes. Este es un servidor en un centro de datos, actuará como nuestro servidor en esta situación, y la llamaremos computadora 2. Es parte de la red C, se le asignó la dirección IP 172.16.1.100 y tiene un servidor web que escucha en el puerto 80.

Un usuario final en la computadora 1 abre un navegador web y escribe 172.16.1.100 en la barra de direcciones. Veamos qué ocurre.

El navegador web que se ejecuta en la computadora 1 sabe que se le ordenó recuperar una página web de 172.16.1.100. El navegador web se comunica con la pila de redes local, que es la parte del sistema operativo responsable de manejar las funciones de red.

El navegador web explica va a querer establecer una conexión TCP a 172.16.1.100, puerto 80. Ahora, la pila de redes va a examinar su propia subred. Ve que está ubicada en la red 10.1.1.0/24, lo que significa que el destino 172.16.1.100 está en otra red.

En este punto, la computadora 1 sabe que tiene que enviar cualquier dato a su puerta de enlace para que lo encamine a una red remota. Y está configurada con una puerta de enlace en 10.1.1.1.

A continuación, la computadora 1 mira su tabla ARP para determinar qué dirección MAC de 10.1.1.1 es, pero no encuentra ninguna entrada correspondiente. Ay, está bien, la computadora A hace una solicitud ARP para una dirección IP de 10.1.1.1, que envía a la dirección de difusión del hardware, que son todas F. Esta solicitud de detección ARP se envía a cada nodo en la red local.

Cuando el router A recibe este mensaje ARP, ve que es la computadora que actualmente tiene asignada la dirección IP 10.1.1.1. Entonces, le responde a la computadora 1 para hacerle saber su propia dirección MAC: 00:11:22:33:44:55.

La computadora 1 recibe esta respuesta y ahora conoce la dirección de hardware de su puerta de enlace. Esto significa que está lista para comenzar a construir el paquete saliente.

La computadora 1 sabe que el navegador web le está pidiendo que forme una conexión TCP saliente, lo que significa que necesitará un puerto TCP de salida. El sistema operativo identifica el puerto efímero 50000 como disponible y abre un socket que conecta el navegador web a este puerto.

Como esta es una conexión TCP, la pila de redes sabe que antes de poder transmitir cualquier dato que el navegador web quiera, tendrá que establecer una conexión. La pila de redes comienza a construir un segmento TCP. Completa todos los campos que corresponden en el encabezado, incluyendo un puerto de origen de 50000 y un puerto de destino 80. Se elige un número de secuencia y se lo usa para completar el campo del número de secuencia. Por último, se establece el indicador SYN, se calcula la suma de verificación para el segmento y se la escribe en el campo de suma de verificación.

Nuestro segmento TCP recién construido ahora se transfiere a la capa IP de la pila de redes. Esta capa construye un encabezado IP. Este encabezado se completa con la IP de origen, la IP de destino y un TTL igual a 64, que es un bonito valor estándar para este campo. A continuación, el segmento TCP se inserta como la carga útil de datos para el datagrama IP. Y se calcula una suma de verificación para todo esto.

Ahora que se construyó el datagrama IP, la computadora 1 necesita enviar esto a su puerta de enlace, que ahora sabe que su dirección MAC es 00:11:22:33:44:55. Por lo tanto, se arma una trama de Ethernet. Todos los campos relevantes se completaron con los datos adecuados, sobre todo, las direcciones MAC de origen y destino. Por último, el datagrama IP se inserta como la carga útil de datos de la trama de Ethernet y se calcula otra suma de verificación.

Ahora tenemos toda una trama de Ethernet lista para enviar a través de la capa física. La interfaz de red conectada a la computadora 1 envía estos datos binarios como modulaciones del voltaje de una corriente eléctrica que atraviesa un cable Cat6 conectado entre la computadora 1 y un conmutador de red.

Este conmutador recibe la trama y luego inspecciona la dirección MAC de destino. El conmutador sabe a cuál de sus interfaces se conecta esta dirección MAC y reenvía la trama sólo a través del cable conectado a esta interfaz.

En el otro extremo de este enlace está el router A, que recibe la trama y reconoce su propia dirección de hardware como destino. El router A sabe que esta trama está destinada a él.

Ahora, toma la totalidad de la trama y le calcula una suma de verificación. El router A compara esta suma de verificación con la que está en el encabezado de la trama de Ethernet y ve que coinciden. Esto significa que todos los datos llegaron sanos y salvos.

A continuación, el router A desarma la trama de Ethernet y se queda con el datagrama IP. De nuevo, realiza una suma de verificación para todo el datagrama. Y una vez más, encuentra que coincide. Es decir, todos los datos son correctos.

Inspecciona la dirección IP de destino y realiza una búsqueda de este destino en su tabla de enrutamiento. El router A ve que para enviar datos a la red 172.16.1.0/24, el camino más rápido está a un salto a través del router B, cuya IP es 192.168.1.1.

El router A mira todos los datos en el datagrama IP, disminuye el TTL en 1, calcula una nueva suma de verificación que refleje ese nuevo valor TTL y hace un nuevo datagrama IP con estos datos.

El router A sabe que necesita enviar este datagrama al router B, cuya dirección IP es 192.168.1.1. Mira su tabla ARP y ve que tiene una entrada para 192.168.1.1.

Ahora, el router A puede comenzar a construir una trama Ethernet con la dirección MAC de su interfaz en la red B como origen, y la dirección MAC en la interfaz del router B en la red B como destino. Una vez que se completaron los valores para todos los campos de esta trama, el router A coloca el datagrama IP recién construido en el campo de carga útil de datos.

Calcula una suma de verificación, la coloca en su lugar y envía la trama a la red B. Al igual que antes, esta trama atraviesa la red B y es recibida por el router B. El router B realiza todas las mismas verificaciones, elimina la encapsulación de la trama Ethernet y realiza una suma de verificación contra el datagrama IP.

Luego examina la dirección IP de destino. Al mirar su tabla de enrutamiento, el router B ve que la dirección de destino de la computadora 2, o 172.16.1.100, está en una red conectada localmente.

Así, disminuye nuevamente en 1 el valor del TTL, calcula una nueva suma de verificación y crea un nuevo datagrama IP. Una nueva trama Ethernet vuelve a encapsular a este nuevo datagrama IP, en este caso, con las direcciones MAC de origen y destino del router B y la computadora 2.

Y todo el proceso se repite por última vez. La trama se envía a la red C, un conmutador asegura que se envíe a la interfaz a la que está conectada la computadora 2.

La computadora 2 recibe la trama, identifica su propia dirección MAC como destino, y sabe que la trama es para ella. La computadora 2 luego quita la trama Ethernet y se queda con el datagrama IP.

Realiza un CRC y reconoce que los datos se entregaron intactos. Luego examina la dirección IP de destino y la reconoce como propia.

A continuación, la computadora 2 desarma el datagrama IP, quedándose solo con el segmento TCP. Una vez más, se examina la suma de verificación para esta capa, y todo concuerda.

Luego, la computadora 2 examina el puerto de destino, que es 80. La pila de redes en la computadora 2 se asegura de que haya un socket abierto en el puerto 80. Ahí está. Está en estado LISTEN y un servidor web Apache en ejecución lo mantiene abierto.

La computadora 2 entonces ve que este paquete tiene el conjunto de indicadores SYN. Entonces examina el número de secuencia y lo guarda, ya que deberá colocar ese número de secuencia en el campo de acuse de recibo una vez que genere la respuesta.

Después de todo eso, todo lo que hemos hecho es enviar un solo segmento TCP que contiene un indicador SYN de una computadora a otra. Todo debería ocurrir una vez más para que la computadora 2 envíe una respuesta SYN-ACK a la computadora 1. Entonces, todo tendría que repetirse una vez más para que la computadora 1 envíe un ACK de nuevo a la computadora 2, y así sucesivamente.

Espero que ver este procedimiento de principio a fin ayude a mostrar cómo todas las diferentes capas de nuestro modelo de red deben trabajar juntas para que todo funcione. Espero que también te dé cierta perspectiva para comprender lo notable que es una red de computadoras.

Aún más notable que eso eres tú, por haber completado todo este módulo. Ahora es el momento de aplicar tu nuevo conocimiento a la próxima evaluación. Cuando termines, te veré en el próximo video. Pero primero, otro cuestionario. Esto ya lo tienes. Pero si no lo entiendes, revisa el material hasta que te sientas más cómodo con estas cosas.
