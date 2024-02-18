> [!TIP]  
> [Ver video](https://youtu.be/b8AqvZup-2k)

Como protocolo, TCP establece conexiones usadas para enviar cadenas largas de segmentos de datos. Usted puede comparar esto con los protocolos que se encuentran mas abajo en el modelo de redes. En ellos se incluyen IP y Ethernet, los cuales envían paquetes individuales de datos. En calidad de Especialista de Soporte TI, usted necesita entender exactamente como funciona, de forma que pueda resolver inconvenientes, donde el trafico de red podría no estar comportándose de la forma esperada.

La forma en que TCP establece una conexión, es a través del uso de diferentes campos de control TCP, usados en un orden muy especifico. Antes de cubrir como las conexiones son establecidas y cerradas, definamos los seis campos de control TCP. Los revisaremos en el orden en que aparecen en el encabezado TCP. Manos a la Obra. No es necesariamente en el mismo orden en el que se encuentran, o en lo importante que son.

El primer campo se conoce como la señal URG, iniciales para Urgente. Un valor de uno aquí indica que el segmento es considerado urgente y que el apuntador urgente tiene mas datos. Como mencionamos en el ultimo video, esta característica de TCP nunca ha tenido un amplio uso y no suele verse.

El segundo campo es la señal ACK, iniciales de acknowledge o reconocido. Un valor uno en este campo significa que el numero de reconocimiento debe ser examinado.

El tercer campo es la señal PSH, iniciales de Push o empujar. Esto significa, que el dispositivo transmisor quiere que el dispositivo receptor empuje datos ya en buffer hacia la aplicación en el receptor tan pronto como sea posible. Un buffer es una técnica de computación, donde una cierta cantidad de datos es guardada en alguna parte, antes de ser enviada a otra. Esto tiene muchas aplicaciones practicas. En términos de TCP, se usa para enviar grandes porciones de datos de forma mas eficiente. Manteniendo alguna cantidad de datos en un buffer, TCP puede entregar mas significativas porciones de datos al programa que los espera. Pero, en algunos casos, usted podría enviar una muy pequeña cantidad de información, que necesita para que el programa que escucha responda inmediatamente. Esto es lo que la señal push hace.

El cuarto campo es la señal RST, iniciales de Resetear, Significa que una de las partes en una conexión TCP no ha sido capas de recuperar apropiadamente una serie de segmentos perdidos o mal formados. Esto se presta para que uno de los compañeros de una conexión TCP básicamente diga, "un momento, no puedo entender lo que dices, empecemos desde el comienzo."

El quinto campo es la señal SYN, iniciales de Synchronize o Sincronizar. Es usada para establecer primero una conexión TCP y asegurarse que el extremo receptor sepa examinar el campo numero de secuencia.

Y finalmente, nuestro campo seis es la señal FIN, iniciales de Fin. Cuando este campo es puesto en uno, significa que el computador transmisor no tiene mas datos que enviar y la conexión puede ser cerrada.

Un buen ejemplo de como campos de control TCP son usados, lo tenemos en como una conexión TCP se establece. El computador A sera nuestro computador transmisor y el computador B sera nuestro computador receptor.

Para empezar el proceso, el computador A, envía un segmento TCP al computador B con el campo en la señal SYN. Esta es una forma para computador A decir, "Establezcamos una conexión y revisa mi numero de secuencia, asi sabremos donde esta conversación inicia."

El computador B luego responde con el segmento TCP, donde las señales SYN y ACK estan listas. Esta es una forma para el computador B decir, "seguro establezcamos una conexión y yo reconozco su numero de secuencia."

Luego el computador A responde de nuevo con la señal ACK, lo cual quiere decir, "Reconozco su reconocimiento. empecemos enviar datos." Me encanta que tan educados son el uno con el otro.

Este intercambio de segmentos que tienen señales SYN, SYN/ACK y ACK, ocurre cada vez que una conexión TCP es establecida en alguna parte. Y es tan popular que lleva un apodo. El choque de manos tripe. Un choque de manos es una forma en la que dos dispositivos aseguran que estan hablando el mismo protocolo y serán capaces de entenderse. Una vez que el choque de manos triple se completa, la conexión TCP es establecida.

Ahora, el computador A es libre de enviar cualquier dato al computador B y vice versa. Debido a que las partes ya se han enviado pares de señales SYN/ACK, una conexión TCP en este estado esta operando en full duplex. Cada segmento enviado en alguna dirección debe ser contestado por el segmento TCP con la señal ACK. De esta forma, la otra parte siempre sabrá lo que ha sido recibido.

Una vez que uno de los dispositivos dentro de la conexión TCP esta listo para cerrar la conexión, ocurre algo conocido como un choque de manos cuádruple. El computador listo para cerrar la conexión, envía una señal FIN. lo cual el otro computador reconoce con la señal ACK. Luego, si el otro computador esta listo también para cerrar la conexión, lo cual sera el caso casi siempre. Enviara una señal FIN. Esto es de nuevo contestado con una señal ACK.

Hipotéticamente, una conexión TCP puede mantenerse abierta en modo simplex con solamente una parte cerrando la conexión. pero esto no es algo que usted vera frecuentemente. A continuación, le mantendré informado, con información sobre estados de Sockets TCP. Es mucho contenido sobre redes. Bien. Nos vemos aquí.
