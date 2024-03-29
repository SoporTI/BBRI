> [!TIP]  
> [Ver video](https://youtu.be/D4LCJr5RP14)

Hasta ahora, aprendimos acerca de las ID de red, que se utilizan para identificar redes, y las ID de host, que se utilizan para identificar hosts individuales. Si queremos dividir un poco más las cosas, y así es, tendremos que introducir un tercer concepto, la ID de subred. Tal vez recuerdes que una dirección IP es solo un número de 32 bits. En un mundo sin subredes, cierto número de estos bits se utilizan para la ID de red y un cierto número de bits se utilizan para la ID de host. En un mundo con subredes, algunos bits que normalmente comprenderían la ID de host se utilizan realmente para la ID de subred. Con estas tres ID que se pueden representar con una sola dirección IP, ahora tenemos un solo número de 32 bits que puede distribuirse con precisión a través de muchas redes diferentes.

A nivel de Internet, los routers centrales solo toman en cuenta la ID de red y lo utilizan para enviar el datagrama al router de la puerta de enlace correspondiente a esa red. Ese router de puerta de enlace tiene información adicional que puede utilizarse para enviar dicho datagrama al equipo de destino o al siguiente router para llegar a su destino. Finalmente, el último router usa la ID de host para entregar el datagrama al equipo destinatario deseado.

Las ID de subred se calculan a través de lo que se conoce como una máscara de subred. Al igual que una dirección IP, las máscaras de subred son números de 32 bits que se escriben, por lo general, como cuatro octetos en sistema decimal.

La forma más sencilla de comprender cómo funcionan las máscaras de subred es comparar una con una dirección IP. Advertencia: a continuación, veremos un tema más denso. Estamos a punto de tratar un tema más complejo, pero es muy importante entender correctamente cómo funcionan las máscaras de subred debido a que con frecuencia se las malinterpreta. A menudo, las máscaras de subred se pasan por alto, como si fueran números mágicos. La gente simplemente memoriza algunas de las más comunes sin entender completamente lo que ocurre fuera de escena.

En este curso tratamos de asegurarnos que recibas una educación completa y sólida sobre la red. Por lo tanto, aunque las máscaras de subred puedan parecer difíciles al principio, no desesperes, en poco tiempo las dominarás. En el siguiente video veremos algunos conceptos básicos adicionales de matemáticas binarias. Si es necesario, puedes ver este video dos o tres veces después de revisar el material. Avanza a tu propio ritmo y lograrás tu objetivo en menos de lo que piensas.

Trabajemos de nuevo con la dirección IP 9.100.100.100. Tal vez recuerdes que cada parte de una dirección IP es un octeto, lo que significa que consta de ocho bits. El número 9 en binario es 1001. Pero debido a que cada octeto necesita ocho bits necesitamos completarlo con ceros adelante. En cuanto a una dirección IP, tener un número 9 como primer octeto se representa, en realidad, como 0000 1001. De manera similar, el número 100 como un número de ocho bits es 0110 0100. Así, toda la representación binaria de la dirección IP 9.100.100.100 es un montón de unos y ceros.

Una máscara de subred es un número binario que tiene dos secciones. La parte inicial, que es la máscara misma, es una cadena de unos. Despúes vienen solo ceros. La máscara de subred, que es la parte del número con todos los unos, nos dice qué podemos ignorar cuando calculamos una ID de host. La parte con todos los ceros nos dice qué debemos mantener.

Utilicemos la máscara de subred común, 255.255.255.0. Esto se traduciría a 24 unos seguidos por 8 ceros. El propósito de la máscara, o la parte que son solo unos, es indicarle a un router qué parte de una dirección IP es la ID de subred. Tal vez recuerdes cómo obtener la ID de red para una dirección IP. Para 9.100.100.100, una red de clase A, sabemos que este es solo el primer octeto. Esto nos deja con los últimos tres octetos.

Tomemos esos octetos restantes e imaginémolos junto a la máscara de subred en forma binaria. Los números en los octetos restantes que tienen un uno correspondiente en la máscara de subred constituyen la ID de subred. Los números en los octetos restantes que tienen un cero correspondiente constituyen la ID del host.

El tamaño de una subred está completamente definido por su máscara de subred. Así, por ejemplo, con la máscara de subred de 255.255.255.0, sabemos que solo el último octeto está disponible para las ID de host, independientemente del tamaño de la red y de las ID de subred.

Un solo número de ocho bits puede representar 256 números diferentes, o más específicamente, los números del 0 al 255. Este es un buen momento para señalar que, en general, una subred generalmente solo puede contener dos números menos que el número total de ID de host disponibles.

De nuevo, al utilizar una máscara de subred de 255.255.255.0, sabemos que el octeto disponible para la ID de host puede contener los números del 0 al 255, pero el 0 por lo general no se usa y el 255 normalmente se reserva como una dirección de difusión para la subred. Esto significa que, en realidad, solo los números del 1 al 254 están disponibles para asignarse a un host.

Si bien este enfoque de "número total menos dos" es casi siempre cierto, en términos generales, te referirás al número de host disponible en una subred como el número entero. Entonces, incluso si se entiende que dos direcciones no están disponibles para la asignación, aún dirías que ocho bits de espacio de ID de host tienen 256 direcciones disponibles, no 254. Esto se debe a que esas otras direcciones IP siguen siendo direcciones IP, incluso si no están asignadas directamente a un nodo en esa subred.

Ahora, veamos una máscara de subred que no traza sus límites en un octeto entero o en ocho bits de una dirección. La máscara de subred 255.255.255.224 se traduciría a 27 unos seguidos de 5 ceros. Esto significa que tenemos cinco bits de espacio de ID de host o un total de 32 direcciones.

Esto nos muestra una forma abreviada de escribir máscaras de subred. Digamos que estamos tratando con nuestra vieja amiga 9.100.100.100 con una máscara de subred de 255.255.255.224. Debido a que esa máscara de subred representa 27 unos seguidos de 5 ceros, una forma más rápida de hacer referencia a esto es con la notación /27. La IP completa y la máscara de subred se pueden escribir ahora como 9.100.100.100/27. Ninguna notación es necesariamente más común que la otra, por lo que es importante entender ambas.

Eso fue bastante por ahora. Asegúrate de volver y ver este video nuevamente si necesitas un repaso, o si eres un completo genio, puedes pasar al siguiente video sobre matemática binaria básica. Nos veremos allí o tal vez aquí de nuevo.
