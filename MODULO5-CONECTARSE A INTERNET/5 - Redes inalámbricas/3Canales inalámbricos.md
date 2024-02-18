> [!TIP]  
> [Ver video](https://youtu.be/OdggGFYRTN4)

# Concepto de Canales en Redes Inalámbricas

El concepto de canales es una de las cosas más importantes a entender sobre redes inalámbricas. Los canales son secciones individuales y más pequeñas de la banda de frecuencia general usada por una red inalámbrica.

Los canales son importantísimos porque permiten abordar un problema de red muy antiguo, los dominios de colisión. Un dominio de colisión es cualquier segmento de red donde una computadora pueda interrumpir a otra. El receptor no puede entender correctamente las comunicaciones superpuestas. Cuando dos o más transmisiones ocurren al mismo tiempo, lo que también se llama "colisión", todos los dispositivos en cuestión tienen que detener sus transmisiones. Esperan una cantidad de tiempo aleatoria e intentan de nuevo cuando las cosas se calman. Esto realmente retrasa las cosas.

El problema causado por los dominios de colisión se redujo principalmente en las redes cableadas mediante dispositivos llamados conmutadores. Los conmutadores recuerdan qué equipos residen en qué interfaces físicas. Por lo tanto, solo se envía tráfico al nodo al que está destinado.

La red inalámbrica no tiene cables, así que no hay interfaces físicas para que un dispositivo inalámbrico se conecte. Eso significa que podemos tener algo que funciona como un conmutador inalámbrico. Los dispositivos inalámbricos están condenados a superponer sus comunicaciones. Los canales ayudan a solucionar este problema en cierta medida.

Cuando estábamos hablando del concepto de las bandas de frecuencia, mencionamos que la radio FM en América del Norte funciona entre 80 MHz y 108 MHz. Pero cuando analizamos las bandas de frecuencia que usamos para Wi-Fi, mencionamos 2.4 GHz y 5 GHz. Esto es porque es una forma abreviada de indicar donde realmente comienzan estas bandas de frecuencia.

Para redes inalámbricas que operan en una banda de 2.4 GHz, lo que realmente queremos decir es que operan aproximadamente en la banda que va 2.4 GHz a 2.5 GHz. Entre estas dos frecuencias hay una cantidad de canales, cada uno con un ancho de una cierta cantidad de MHz.

Como diferentes países y regiones tienen diferentes comités reguladores para el uso de las frecuencias de radio, la cantidad exacta de canales disponibles para usar depende de la parte del mundo en que te encuentres.

Por ejemplo, al tratar con una red 802.11b, el canal 1 opera a 2412 MHz, pero como el ancho del canal es de 22 MHz, la señal realmente reside en las frecuencias entre 2401 MHz y 2423 MHz. Esto es porque las ondas de radio son cosas imprecisas. Por lo tanto, necesitas cierto margen en torno a las frecuencias exactas en las que puede llegar una transmisión.

Algunos canales se superponen, otros están lo suficientemente separados para no interferir entre sí en absoluto. Veamos nuevamente la red 802.11b que opera en una banda de 2.4 GHz, porque realmente es la más simple y los conceptos se traducen a todas las demás especificaciones 802.11.

Con un ancho de canal de 22 MHz, el canal 1, con su punto medio en 2412 MHz, siempre está completamente aislado del canal 6 cuyo punto medio está en 2437 MHz. Para una red 802.11b, esto significa que los canales 1, 6 y 11 son los únicos que nunca se superponen en absoluto.

Sin embargo, eso no es todo lo que importa. Hoy en día, la mayoría de los equipos de redes inalámbricas están desarrollados para detectar automáticamente qué canales están más congestionados. Algunos puntos de acceso solo realizarán este análisis cuando se inicien, otros cambiarán dinámicamente su canal según sea necesario.

Entre esas dos situaciones y canales especificados manualmente, todavía puedes encontrarte en situaciones en las que experimentas una gran congestión de canales. Esto es especialmente cierto en densas zonas urbanas con muchas redes inalámbricas en las proximidades.

Entonces, ¿por qué es esto importante en el mundo del soporte de TI? Bueno, entender cómo estos canales se superponen para todas las especificaciones 802.11 es una forma en la que puedes ayudar a solucionar problemas de mala conectividad inalámbrica o pérdida de velocidad en la red. Desearás evitar los dominios de colisión siempre que puedas.

Debo señalar que no es importante memorizar todos los números individuales de los que hemos hablado. Lo importante es entender cómo los dominios de colisión son un problema inevitable en todas las redes inalámbricas, y cómo puedes usar tus conocimientos en este espacio para optimizar las implementaciones de redes inalámbricas. Debes asegurarte de que tus propios puntos de acceso y los de empresas vecinas superpongan sus canales lo menos posible.
