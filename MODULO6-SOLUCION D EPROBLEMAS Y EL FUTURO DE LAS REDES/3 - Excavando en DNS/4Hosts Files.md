Mucho antes de que DNS fuera una tecnología establecida y globalmente disponible, era obvio para los operadores de computadoras que necesitaban un sistema basado en lenguaje para referirse a los dispositivos de red. Ya hablamos de cómo los humanos somos mucho mejores recordando palabras descriptivas que números. Pero los números representan la forma natural en que las computadoras piensan y se comunican.

La forma original en que las direcciones de red numeradas se correlacionaron con las palabras fue a través de archivos de hosts. Un archivo de host es un archivo plano que contiene, en cada línea, una dirección de red seguida del nombre de host a la que puede hacer referencia. Por ejemplo, una línea en un archivo host puede decir "1.2.3.4 webserver". Esto significa que en la computadora donde reside este archivo host, un usuario podría simplemente referirse al servidor web ("webserver") en lugar de la IP 1.2.3.4.

Los archivos de hosts son evaluados por la pila de redes del propio sistema operativo. Eso implica que la presencia de una entrada allí se traduciría como cualquier lugar al que una dirección de red pueda hacer referencia. Siguiendo con nuestro ejemplo anterior, un usuario podría escribir "webserver" en una barra de URL de un navegador web o podría emitir un comando "ping webserver" y, en cualquier caso, se traduciría a 1.2.3.4.

Los archivos de hosts pueden ser una tecnología antigua, pero se han mantenido todo este tiempo. Todos los SO modernos, incluidos los que hacen funcionar a nuestros teléfonos y tablets, todavía tienen archivos de hosts. Un motivo es debido a una dirección IP especial que aún no hemos visto: la dirección de loopback. Una dirección de loopback siempre apunta a sí misma. Por lo tanto, una dirección de loopback es una forma de enviar tráfico de red a ti mismo. El envío de tráfico a una dirección de loopback evita toda la infraestructura de la red en sí, y el tráfico nunca abandona el nodo. La IP de loopback para IPv4 es 127.0.0.1. Y hasta el día de hoy, se la sigue configurando en todos los SO modernos a través de una entrada en un archivo host. Casi todos los archivos de hosts que existen al menos contendrán una línea que dice "127.0.0.1 localhost," muy probablemente seguida por ":: 1 localhost", donde ":: 1" es la dirección de loopback para IPv6.

Como DNS está en todas partes, los archivos de hosts ya no se usan tanto. Pero todavía existen y es importante conocerlos. Algunos programas incluso requieren entradas específicas en los archivos de hosts para funcionar correctamente, a pesar de lo anticuado que puede parecer esta práctica.

Por último, los archivos de hosts son una forma popular con la que los virus informáticos interrumpen y redireccionan el tráfico del usuario. No es una buena idea usar archivos de hosts actualmente. Pero tienen ciertos fines útiles de resolución de problemas que pueden servir de ayuda en el soporte de TI. Los archivos de hosts se examinan antes de que se produzca un intento de resolución de DNS en casi todos los SO principales. Esto te permite forzar a una computadora individual a que piense que un determinado nombre de dominio siempre apunta a una IP específica.

¿Lo entendiste? Hemos visto mucho material. Tómate un tiempo para repasar si lo necesitas y asegúrate de entender los conceptos que estamos analizando. A continuación, un breve cuestionario.