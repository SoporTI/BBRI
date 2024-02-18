> [!TIP]  
> [Ver video](https://youtu.be/Wk1EVK_wa9k)

Vimos un montón de maneras de probar la conectividad entre máquinas en la capa de red. Pero a veces, necesitas saber si las cosas funcionan en la capa de transporte. Para esto, hay dos herramientas poderosísimas a tu disposición: Netcat en Linux y Mac OS y Test-NetConnection en Windows.

La herramienta Netcat se puede ejecutar a través del comando nc, y tiene dos argumentos obligatorios, un host y un puerto. Al ejecutar `nc google.com 80`, se intentaría establecer una conexión en el puerto 80 a google.com. Si la conexión falla, el comando finalizará. Si tiene éxito, verás un cursor que parpadea a la espera de más entradas. Esta es una forma de enviar datos de la capa de aplicación al servicio que escucha desde tu propio teclado.

Si tienes verdadera curiosidad sobre el estado de un informe, puedes emitir el comando con una marca -Z, que significa Zero Input/Output Mode (modo cero de E/S). La marca -V, que significa Verbose (detallado), también es útil en esta situación. Esto hace que los comandos emitan una salida útil para el ojo humano a diferencia de la salida no detallada, que es mejor para el uso en secuencias de comandos.

Nota al margen: "Detallada" básicamente significa "que habla demasiado". Apuesto que quieres ponernos una marca a mí y a mi parloteo, pero todavía tenemos mucho para ver.

De acuerdo, entonces, al emitir el comando Netcat con las marcas -Z y -V, la salida del comando simplemente te dirá si es posible o no una conexión al puerto en cuestión.

En Windows, Test-NetConnection es un comando con cierta funcionalidad similar. Si ejecutas `Test-NetConnection` con solo un host especificado, de manera predeterminada usará una solicitud de eco ICMP, al igual que el programa de ping. Pero aparecerán muchos más datos, entre ellos, el protocolo de capa de enlace de datos en uso.

Cuando emites `Test-NetConnection` con la marca -port, puedes pedirle que pruebe la conectividad a un puerto específico.

Cabe señalar que tanto Netcat como Test-NetConnection son mucho más potentes que los breves ejemplos de conectividad de puertos que vimos aquí. De hecho, son herramientas tan complejas que abarcar toda su funcionalidad sería demasiado para un video. Deberás informarte sobre todas las demás cosas que estas herramientas poderosísimas pueden hacer. Podrás encontrar algo en las lecturas complementarias. Y una vez que hayas tenido la oportunidad de leer todo el material, habrá un breve cuestionario para ti.
