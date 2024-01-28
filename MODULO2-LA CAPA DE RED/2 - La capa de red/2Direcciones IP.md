Las direcciones IP tienen números de 32 bits
compuestos por 4 octetos y cada octeto se describe normalmente
en números decimales. Ocho bits de datos, o un solo octeto, pueden representar todos los números decimales
del 0 al 255. Por ejemplo, la dirección 12.34.56.78 es una IP válida. Sin embargo, la dirección 123.456.789.100 no lo sería porque tiene números más grandes
que los que se podrían representar mediante 8 bits. Este formato se conoce como
notación decimal con puntos.

Profundizaremos más sobre la manera cómo
parte de esto funciona en una próxima lección sobre subredes. Lo importante que debes saber por ahora
es que las direcciones IP se distribuyen en grandes secciones a diversas organizaciones y compañías, y no las determinan los proveedores de hardware.

Esto significa que las direcciones IP
son más jerárquicas y almacenan datos más fácilmente
que las direcciones físicas. Ten presente a IBM, que posee cada IP
que tenga el número 9 como primer octeto. A un nivel muy alto, esto significa
que si un router de Internet necesita saber dónde enviar un paquete de datos
destinado a la dirección IP 9.0.0.1, ese router solo necesita saber
que debe enviarlo a uno de los routers de IBM. Dicho router puede gestionar el resto
del proceso de entrega a partir de allí.

Es importante enfatizar que las direcciones IP
pertenecen a las redes, no a los dispositivos conectados
a esas redes. De esta forma, tu laptop siempre tendrá la misma dirección MAC,
no importa donde la utilices. Pero una dirección IP asignada en un cibercafé
será diferente a la que tendría tu laptop si estuvieras en casa. La red de área local (LAN) en el cibercafé
o la LAN de tu casa serían cada una responsable individualmente de asignar una dirección IP
a tu laptop si la enciendes en alguno de estos lugares.

En el día a día, obtener una dirección IP es generalmente
un proceso imperceptible. Aprenderás más sobre algunas de las tecnologías
que entran en juego en una lección posterior. Por ahora, recuerda que puedes conectar un nuevo dispositivo
en cualquiera de las redes modernas, y se le asignará una dirección IP automáticamente a través de una tecnología conocida como
Protocolo de configuración dinámica de host (DHCP). Una dirección IP asignada de esta manera
se conoce como una dirección IP dinámica. Lo contrario de esto se conoce
como una dirección IP estática, la que debe configurarse en un nodo
de manera manual. En la mayoría de los casos, las direcciones IP estáticas
están reservadas para servidores y dispositivos de red, mientras que las IP dinámicas
están reservadas para los clientes. Sin embargo, existen ciertas situaciones
en las que esto no es del todo cierto.
