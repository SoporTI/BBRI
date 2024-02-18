> [!TIP]  
> [Ver video](https://youtu.be/h-EMs7DXENY)

Cuando IPv6 estaba en desarrollo, se tomaron el tiempo para introducir algunas mejoras en lugar de descubrir la manera para aumentar el tamaño de la dirección. Esto debería ser un alivio para ti, y los especialistas en soporte de TI aman las redes que funcionan bien.

Una de las mejoras más elegantes se hizo en el encabezado de IPv6, que es mucho más simple que el de IPv4. El primer campo en un encabezado IPv6 es el campo de la versión. Este es un campo de 4 bits que define qué versión de IP está en uso. Quizás recuerdes que un encabezado IPv4 comienza exactamente con este mismo campo.

El siguiente campo se llama campo de clase de tráfico. Este es un campo de 8 bits que define el tipo de tráfico contenido en el datagrama IP y da cuenta de diferentes clases de tráfico para que reciban diferentes prioridades.

El siguiente campo es el campo de la etiqueta de flujo. Este es un campo de 20 bits que se usa junto con el campo de clase de tráfico para que los routers tomen decisiones sobre la calidad del nivel de servicio para un datagrama específico.

A continuación tienes el campo de longitud de carga útil. Este es un campo de 16 bits que define cuánto mide la sección de carga útil de datos del datagrama.

Luego tienes el campo de encabezado siguiente. Este es un concepto exclusivo de IPv6 y requiere una breve explicación adicional. Las direcciones IPv6 son cuatro veces más largas que las direcciones IPv4. Eso significa que tienen más unos y ceros, lo que implica más tiempo en ser transmitidas a través de un enlace. Para reducir problemas con los datos adicionales que imponen las direcciones IPv6 en la red, el encabezado IPv6 se desarrolló para que sea lo más corto posible.

Una forma de hacerlo es tomar todos los campos opcionales y abstraerlos del mismo encabezado de IPv6. El campo de encabezado siguiente define qué tipo de encabezado viene inmediatamente después del actual. Estos encabezados adicionales son opcionales, por lo que no son necesarios para un datagrama IPv6 completo. Cada uno de estos encabezados opcionales adicionales contienen un campo de encabezado siguiente y dan cuenta de la formación de una cadena de encabezados si hay mucha configuración opcional.

A continuación tenemos lo que se llama el campo de límite de salto. Este es un campo de 8 bits cuyo propósito es idéntico al del campo TTL en un encabezado IPv4.

Por último, tenemos los campos de dirección de origen y destino, que tienen 128 bits cada uno. Si el campo de encabezado siguiente especifica otro encabezado, seguiría ahora. Si no, vendría una carga útil de datos de la misma longitud que se especifica en el campo de longitud de la carga útil.
