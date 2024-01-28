Un servicio proxy es un servidor que actúa en nombre de un cliente con el fin de acceder a otro servicio. Los proxies se ubican entre los clientes y otros servidores, y proporcionan ciertos beneficios adicionales: anonimato, seguridad, filtrado de contenidos, mayor desempeño, un par de otras cosas. Si algo de esto suena familiar, eso es bueno. Ya hemos visto algunos ejemplos específicos de proxies, como routers de puerta de enlace. No escucharás que los mencionen de esta manera, pero una puerta de enlace definitivamente cumple con la definición y el funcionamiento de un proxy.

El concepto de proxy es solo eso, un concepto o una abstracción. No se refiere a ninguna implementación específica. Los proxies existen en casi todas las capas de nuestro modelo de red. Hay docenas y docenas de ejemplos de proxies que podrías encontrar en tu carrera, pero aquí vamos a ver solo algunos de los más comunes.

Muy a menudo, oirás el término proxy, que se utiliza para referirse a proxies web. Como podrás imaginar, estos son proxies específicamente construidos para el tráfico web. Un proxy web puede cumplir con muchas funciones. Hace muchos años, cuando la mayoría de las conexiones de Internet eran mucho más lentas de lo que son hoy, muchas organizaciones usaban proxies web para mayor desempeño. Con un proxy web, una organización dirigiría todo el tráfico web a través de él, lo que le permite en sí recuperar realmente los datos de la página web desde Internet. Luego, almacenará estos datos en caché. De esta manera, si alguien más solicita la misma página web, simplemente podría devolver los datos guardados en el caché en lugar de tener que recuperar una copia nueva cada vez.

Este tipo de proxy es bastante antiguo y no sueles encontrarlos en uso hoy en día. ¿Por qué? Bueno, en primer lugar, la mayoría de las organizaciones ahora tienen conexiones suficientemente rápidas, por lo que guardar páginas web individuales en caché no ofrece gran beneficio. Además, la web se volvió mucho más dinámica. Ir a www.twitter.com va a ser diferente para cada persona con su propia cuenta de Twitter, por lo que almacenar en caché estos datos no sirve de mucho.

Un uso más común de un proxy web hoy en día podría ser para evitar que alguien acceda por completo a sitios como Twitter. Una empresa podría decidir que acceder a Twitter durante las horas de trabajo reduce la productividad. Con un proxy web, puede dirigir todo el tráfico web a él, permitir que el proxy inspeccione qué datos se solicitan, y luego permitir o rechazar esta solicitud según el sitio al que se quiera acceder.

Otro ejemplo de proxy es un proxy inverso. Un proxy inverso es un servicio que a los clientes externos puede parecerles un solo servidor, pero en realidad representa a muchos servidores detrás de él. Un buen ejemplo de esto es la arquitectura de muchos de los sitios web populares de hoy. Sitios web muy populares, como Twitter, reciben tanto tráfico que no hay forma en que un solo servidor web pueda posiblemente manejarlo todo.

Un proxy inverso, en esta situación, podría actuar como un único frontend para muchos servidores web ubicados detrás de él. Desde la perspectiva de los clientes, parece que todos están conectados al mismo servidor. Pero detrás de escena, este servidor proxy inverso, en realidad, está distribuyendo estas solicitudes entrantes a muchos servidores físicos diferentes. Al igual que en el concepto de round robin de DNS, esta es una forma de equilibrio de carga.

Otra forma en que los sitios web populares usan comúnmente los proxies inversos es manejar la desencriptación. Más de la mitad de todo el tráfico en la web ahora está encriptado, y encriptar y desencriptar datos es un proceso que puede requerir mucha potencia de procesamiento. Aprenderás mucho más sobre la encriptación y cómo funciona en otro curso en este programa. Los proxies inversos ahora se implementan para utilizar hardware compilado específicamente para criptografía con el objeto de hacer tareas de encriptación y desencriptación. Así, los servidores web están libres para entregar contenido.

Hay gran variedad de proxies, son demasiados para que los veamos todos aquí. Pero lo más importante es entender que un servidor proxy es cualquier servidor que actúe como intermediario entre un cliente y otro servidor.

Buen trabajo, hemos visto muchos temas. Descansa un poco antes de pasar al cuestionario y al proyecto que preparamos para ti. Cuando termines con todo, toma otro descanso y luego nos encontramos aquí para el siguiente módulo, en el que hablaremos de la historia de las conexiones a Internet.