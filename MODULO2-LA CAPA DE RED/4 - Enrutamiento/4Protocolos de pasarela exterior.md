> [!TIP]  
> [Ver video](https://youtu.be/z_gNmNP6HAw)

Los **protocolos de puerta de enlace exterior** se usan para comunicar datos entre routers que representan el perímetro de un sistema autónomo. Como los routers que comparten datos usando protocolos de puerta de enlace interior están todos bajo el control de la misma organización, los routers usan protocolos de puerta de enlace exterior cuando necesitan compartir información entre diferentes organizaciones.

Los protocolos de puerta de enlace exterior son realmente claves para que Internet funcione como lo hace hoy. Así, gracias a los protocolos de puerta de enlace exterior, Internet es una enorme malla de sistemas autónomos.

En los niveles superiores, los routers centrales de Internet necesitan saber sobre los sistemas autónomos con el fin de reenviar correctamente el tráfico. Dado que los sistemas autónomos son conjuntos conocidos y definidos de redes, enviar datos al router perimetral de un sistema autónomo es el objetivo número uno de los routers centrales de Internet.

La **IANA**, o *Internet Assigned Numbers Authority*, es una organización sin fines de lucro que ayuda a administrar cosas como la asignación de direcciones IP. Internet no podría funcionar sin una sola autoridad para este tipo de cuestiones. De lo contrario, cualquiera podría intentar usar cualquier espacio IP que quisiera, lo que causaría un caos total en línea.

Junto con la gestión de la asignación de direcciones IP, IANA también es responsable de **ASN**, o *asignación de números de sistemas autónomos*. Los ASN son números asignados a sistemas autónomos individuales. Al igual que las direcciones IP, los ASN son números de 32 bits. Pero, a diferencia de las direcciones IP, en general se los menciona como un solo número decimal, en lugar de dividirlos en bits legibles.

Hay dos razones para esto. Primero, las direcciones IP necesitan poder representar una parte de ID de red y una parte de ID de host para cada número. Esto se logra con más facilidad dividiendo el número en cuatro secciones de ocho bits, especialmente en aquellos días en que las clases de dirección dominaban el mundo. Un ASN nunca necesita cambiar para representar más redes o hosts. Solo hace falta actualizar las tablas de enrutamiento centrales de Internet para saber qué representa un ASN.

En segundo lugar, los humanos vemos un ASN con mucha menos frecuencia que una dirección IP. Entonces, ya que puede ser útil ver la IP 9.100.100.100 y saber que el espacio de direcciones 9.0.0.0/8 es propiedad de IBM, los ASN representan sistemas autónomos completos. Con solo el hecho de ver que AS19604 pertenece a IBM es suficiente.

A menos que algún día termines trabajando en un proveedor de servicios de Internet, entender más detalles sobre cómo funcionan los protocolos de puerta de enlace exterior está fuera del alcance de la mayoría de las personas en TI. Pero comprender los fundamentos de los sistemas autónomos, los ASN y cómo los routers centrales de Internet dirigen el tráfico entre ellos es importante para entender algunos de los fundamentos básicos de Internet.
