> [!TIP]  
> [Ver video](https://youtu.be/9du4BcIyx30)

**Aviso:** En este video, vamos a diseccionar un segmento TCP. En soporte de TI, si el tráfico de red no se comporta como los usuarios esperan, tal vez debas analizarlo de cerca para solucionar problemas. Por lo tanto, prepárate para husmear el funcionamiento interno.

Así como una trama de Ethernet encapsula un datagrama IP, un datagrama IP encapsula un segmento TCP. Recuerda que una trama de Ethernet tiene una sección de carga útil que, en realidad, es todo el contenido de un datagrama IP. Recuerda también que un datagrama IP tiene una sección de carga útil compuesta por lo que se conoce como un segmento TCP. Un segmento TCP se compone de un encabezado TCP y una sección de datos. Esta sección de datos, como puedes suponer, es solo otra área de carga útil donde la capa de aplicación coloca sus datos.

En sí, un encabezado TCP se divide en muchos campos que contienen mucha información. Primero, tenemos los campos del puerto de origen y el puerto de destino. El puerto de destino es el puerto del servicio al que está destinado el tráfico, algo que analizamos en el último video. Un puerto de origen es un puerto con numeración alta, seleccionado de una sección especial de puertos conocidos como "efímeros". Hablaremos sobre los puertos efímeros con más detalle en un momento. Por ahora, es suficiente saber que se requiere un puerto de origen para mantener separadas muchas conexiones salientes.

¿Recuerdas cómo un puerto de destino, digamos el puerto 80, es necesario para garantizar que el tráfico llegue a un servidor web que se ejecuta en una determinada IP? Del mismo modo, se necesita un puerto de origen para que cuando el servidor web responda, la computadora que realiza la solicitud original pueda enviar estos datos al programa que los estaba solicitando. Así, cuando el servidor web responde a tus solicitudes para ver una página web, el que recibe esta respuesta es tu navegador web, no tu procesador de texto.

El siguiente es un campo conocido como número de secuencia. Es un número de 32 bits que se utiliza para rastrear en qué lugar de una secuencia de segmentos TCP se espera encontrar un segmento en particular. Tal vez recuerdes que más abajo en nuestra pila de protocolos, hay límites al tamaño total de lo que enviamos a través del cable. En una trama de Ethernet, esto generalmente se limita a un tamaño de 1,518 bytes, pero normalmente necesitamos enviar más datos que esos. En la capa de transporte, TCP divide todos estos datos en muchos segmentos. El número de secuencia en un encabezado se utiliza para rastrear qué segmento de entre muchos otros podría ser este segmento en particular.

El siguiente campo, el número de acuse de recibo, es muy parecido al número de secuencia. El número de acuse de recibo es el número del siguiente segmento esperado. En palabras muy simples, un número de secuencia igual a uno y un número de confirmación igual a dos podría interpretarse como que este es el segmento uno y que se espera el segmento dos a continuación.

A continuación viene el campo de longitud del encabezado. Este campo es un número de cuatro bits que comunica la longitud del encabezado TCP para este segmento. Esto es para que el dispositivo receptor de red comprenda dónde comienza la carga útil real de datos.

Luego, tenemos seis bits que están reservados para los seis indicadores de control de TCP. Veremos los indicadores de control y lo que significan en el siguiente video; márcalo para más adelante.

El siguiente campo es un número de 16 bits conocido como ventana TCP. Una ventana TCP especifica el rango de números de secuencia que pueden enviarse antes de que se requiera un acuse de recibo. Como veremos en detalle pronto, TCP es un protocolo que depende en gran medida de los acuses de recibo. Esto se hace para asegurarse de que se reciban realmente todos los datos que se esperan y que el dispositivo de envío no pierda tiempo enviando datos que no se reciben.

El siguiente campo es una suma de verificación de 16 bits. Funciona igual que los campos de suma de comprobación a nivel de IP y Ethernet. Una vez que un destinatario recibe todo este segmento, se calcula la suma de comprobación de todo el segmento y se compara con la suma de comprobación del encabezado para asegurarse de que no se hayan perdido o dañado datos en el camino.

El campo del puntero urgente se usa junto con uno de los indicadores de control TCP para señalar segmentos particulares que podrían ser más importantes que otros. Esta es una función de TCP que nunca se ha adoptado y que probablemente nunca encuentres en redes modernas. Aun así, es importante saber qué son todas las secciones del encabezado TCP.

A continuación, tenemos el campo de opciones. Al igual que el campo del puntero urgente, esto raramente se usa en el mundo real, pero a veces se usa para protocolos de control de flujo más complicados.

Por último, tenemos un relleno que es solo una secuencia de ceros para asegurarnos de que la sección de carga útil de datos comience en la ubicación esperada.
