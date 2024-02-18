> [!TIP]  
> [Ver video](https://youtu.be/N_RaVlIGuEI)

# NAT en la Capa de Transporte

NAT en la capa de red es bastante fácil de entender. Un dispositivo, generalmente un router, traduce una dirección IP en otra. Pero en la capa de transporte, las cosas se complican un poco más y varias técnicas adicionales entran en juego para asegurarse de que todo funcione correctamente.

En NAT uno a muchos hablamos de cómo cientos, incluso miles de computadoras pueden tener su tráfico saliente traducido mediante NAT a una sola IP. Esto es bastante fácil de entender cuando el tráfico es saliente, pero un poco más complicado cuando involucra al tráfico de retorno. Ahora tenemos, potencialmente, cientos de respuestas dirigidas a la misma IP, y el router en esta IP necesita determinar qué respuestas van a qué computadora.

La forma más sencilla de hacer esto es a través de la conservación de puertos. La conservación de puertos es una técnica en la que el puerto de origen elegido por un cliente es el mismo puerto que usa el router. Recuerda que las conexiones salientes eligen un puerto de origen al azar de entre los puertos efímeros o los puertos en el rango de 49,152 a 65,535. En la configuración más sencilla, una configuración de router para tráfico saliente NAT, solo controlaremos qué puerto de origen es este y lo usaremos para dirigir el tráfico de regreso a la computadora correcta.

Imaginemos un dispositivo con una IP de 10.1.1.100. Quiere establecer una conexión saliente y la pila de redes del SO elige el puerto 51,300 para esta conexión. Una vez que esta conexión saliente llega al router, realiza la traducción de direcciones de red y coloca su propia IP en el campo de dirección de origen del datagrama IP, pero no cambia el puerto de origen en el datagrama TCP y almacena estos datos internamente en una tabla. Ahora, cuando el tráfico regresa al router y al puerto 51,300, sabe que este tráfico debe reenviarse a la IP 10.1.1.100.

A pesar del tamaño del conjunto de puertos efímeros, todavía es posible que dos computadoras diferentes en una red elijan el mismo puerto de origen al mismo tiempo. Cuando esto sucede, por lo general el router selecciona un puerto no utilizado al azar para usar en su lugar.

Otro concepto importante sobre NAT y la capa de transporte es la redirección de puertos. La redirección de puertos es una técnica en la que puertos específicos de destino se pueden configurar para que siempre se entreguen a nodos específicos. Esta técnica permite un enmascaramiento completo de IP sin dejar de tener servicios que puedan responder al tráfico entrante.

Usemos nuestra red 10.1.1.0/24 nuevamente para demostrar esto. Supongamos que hay un servidor web configurado con una IP de 10.1.1.5. Con la redirección de puertos, nadie tendría que conocerla. Los posibles clientes web solo tendrían que conocer la IP externa del enrutador. Supongamos que es 192.168.1.1. Cualquier tráfico dirigido al puerto 80 en 192.168.1.1 se reenviaría automáticamente a 10.1.1.5. El tráfico de respuesta tendría la IP de origen reescrita para que se parezca a la IP externa del router.

Esta técnica no solo permite el enmascaramiento IP, sino también simplifica la interacción de los usuarios externos con una gran cantidad de servicios ejecutados por la misma organización. Imaginemos una empresa con un servidor web y un servidor de correo; ambos necesitan ser accesibles al mundo exterior, pero se ejecutan en diferentes servidores con diferentes IP. Una vez más, digamos que el servidor web tiene una IP de 10.1.1.5, y el servidor de correo tiene una IP de 10.1.1.6. Con la redirección de puertos, el tráfico para cualquiera de estos servicios podría dirigirse a la misma IP externa y, por lo tanto, al mismo nombre DNS, pero se entregaría a servidores internos completamente diferentes debido a sus diferentes puertos de destino.
