> [!TIP]  
> [Ver video](https://youtu.be/VGJJpHWeobk)

# Privacidad y Seguridad en Redes Inalámbricas

Cuando estás enviando datos a través de un enlace por cable, tu comunicación tiene un cierto grado de privacidad inherente. Los únicos dispositivos que realmente saben qué datos se están transmitiendo son los dos nodos en cada extremo del enlace. Alguien o algún dispositivo que se encuentre cerca no puede leer los datos.

Con la red inalámbrica, este no es realmente el caso, ya que no hay cables, sólo transmisiones de radio transmitidas por el aire. Cualquier persona dentro del alcance podría interceptar hipotéticamente cualquier transmisión, estuviera o no destinada para sí.

Para resolver este problema, se inventó WEP. **WEP** significa "Privacidad Equivalente al Cableado" y es una tecnología de encriptación que proporciona un nivel de privacidad muy bajo. En realidad, su nombre lo describe, es la privacidad equivalente a la de una red cableada. Al usar WEP proteges tus datos un poco, pero en realidad, solo debería verse tan seguro como enviar datos sin encriptar a través de una conexión por cable.

El estándar WEP es un algoritmo de encriptación muy débil. No hace falta mucho tiempo para que un malhechor pueda quebrar esta encriptación y leer tus datos. Aprenderás más sobre longitud de claves y encriptación en un futuro curso. Pero por ahora, es importante saber que el número de bits en una clave de encriptación equivale a su nivel de seguridad. Cuantos más bits tenga una clave, más tiempo le tomará a alguien resolver la encriptación. WEP solo usa 40 bits para sus claves de encriptación y, con la velocidad de las computadoras modernas, en general esto se puede descifrar en unos pocos minutos.

En muchos lugares, WEP se reemplazó rápidamente con **WPA**, o Acceso Protegido a Wi-Fi. WPA, de manera predeterminada, utiliza una clave de 128 bits, lo que hace que sea mucho más difícil de descifrar que WEP. Hoy en día, el algoritmo de encriptación más utilizado para redes inalámbricas es **WPA2**, una actualización al WPA original. WPA2 utiliza una clave de 256 bits que lo hace aún más difícil de descifrar.

Otra forma común de ayudar a proteger las redes inalámbricas es a través del **Filtrado MAC**. Con el filtrado MAC, configuras tus puntos de acceso para permitir solo conexiones desde un conjunto específico de direcciones MAC que pertenecen a dispositivos en los que confías. Esto no hace nada más para ayudar a encriptar el tráfico inalámbrico que se envía a través del aire, pero sí proporciona una barrera adicional que impide que dispositivos no autorizados se conecten a la propia red inalámbrica.