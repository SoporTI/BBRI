> [!TIP]  
> [Ver video](https://youtu.be/FWfhTXWxoGg)

Durante nuestro video anterior sobre los conceptos básicos del enrutamiento, tal vez notaste un montón de referencias a algo conocido como una tabla de enrutamiento. El enrutamiento en sí es un concepto bastante simple y verás que las tablas de enrutamiento no son mucho más complicadas.

Los primeros routers eran simplemente las computadoras comunes de ese momento. Tenían dos interfaces de red, un puente a las redes y una tabla de enrutamiento automático que se actualizaba manualmente. De hecho, todos los principales sistemas operativos actuales siguen teniendo una tabla de enrutamiento que consultan antes de transmitir datos. Todavía podrías construir tu propio router hoy si tuvieras una computadora con dos interfaces de red y actualizaras la tabla de enrutamiento a mano.

Las tablas de enrutamiento pueden variar muchísimo según la marca y la clase del router, pero todas tienen algunas cosas en común. La tabla de enrutamiento más básica tendrá cuatro columnas.

Red de destino: esta columna contendrá una fila para cada red que el router conoce, esto es exactamente la definición de la red remota, una ID de red y la máscara de red. Podrán almacenarse en una columna dentro de una notación, o la ID de red y la máscara de red pueden estar en una columna separada. De cualquier manera, es el mismo concepto, el router tiene una definición para una red y, por lo tanto, sabe qué direcciones IP pueden existir en esa red. Cuando el router recibe un paquete entrante, examina la dirección IP de destino y determina a qué red pertenece. Una tabla de enrutamiento generalmente tendrá una entrada genérica que coincida con cualquier dirección IP para la que no tenga una lista de red explícita.

Siguiente salto: esta es la dirección IP del siguiente router que debe recibir los datos destinados a la red de destino en cuestión, o bien podría simplemente indicar que la red está conectada directamente y no se necesitan saltos adicionales.

Saltos totales: esto es crucial para entender el enrutamiento y cómo funcionan las tablas de enrutamiento. En cualquier red compleja, como Internet, habrá muchos caminos diferentes para llegar desde el punto A al punto B. Los routers intentan elegir el camino más corto posible todo el tiempo para garantizar la entrega oportuna de los datos, pero el camino más corto posible para una red de destino es algo que podría cambiar con el tiempo, a veces, rápidamente: los routers intermedios podrían quedar fuera de servicio, los enlaces podrían desconectarse, podrían incorporarse nuevos routers, la congestión del tráfico puede hacer que ciertas rutas se vuelvan demasiado lentas para usar. En un próximo video, sabremos cómo los routers detectan la ruta más corta. Por ahora, es importante saber que para cada próximo salto y cada red de destino, el router deberá rastrear a qué distancia se encuentra ese destino actualmente. De esa manera, cuando recibe información actualizada de routers vecinos, sabrá si conoce actualmente el mejor camino o si hay un nuevo mejor camino disponible.

Interfaz: el router también tiene que saber a cuál de sus interfaces debe reenviar el tráfico que coincida con la red de destino.

En la mayoría de los casos, las tablas de enrutamiento son bastante simples. Lo realmente impresionante es que muchos routers centrales de Internet tienen millones de filas en las tablas de enrutamiento. Se las debe consultar para cada paquete que fluye a través de un router en su camino hacia su destino final.

Lo que también es impresionante es lo que aprendiste sobre routers, enrutamiento y tablas de enrutamiento. Buen trabajo. Te veré en el siguiente video sobre los protocolos de puerta de enlace interior.