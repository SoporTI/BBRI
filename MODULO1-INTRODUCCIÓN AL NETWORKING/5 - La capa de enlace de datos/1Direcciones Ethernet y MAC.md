> [!TIP]  
> [Ver video](https://youtu.be/--FPsh0D8ek)

# El acceso inalámbrico y celular a Internet

El acceso inalámbrico y celular a Internet se está convirtiendo rápidamente en una de las formas más comunes para conectar dispositivos informáticos a redes, y probablemente es cómo estés conectado ahora. Tal vez te sorprenda escuchar que las redes de cable tradicionales siguen siendo la opción más común que encontrarás en tu lugar de trabajo y, definitivamente, en el centro de datos.

El protocolo que más se usa para enviar datos a través de enlaces individuales se conoce como Ethernet. Ethernet y la capa de enlace de datos proporcionan un medio para que el software en los niveles más altos de la pila envíe y reciba datos. Básicamente, uno de los propósitos principales de esta capa es abstraer la necesidad de que otras capas se hagan cargo de la capa física y del hardware en uso. Al transferir esta responsabilidad a la capa de enlace de datos, las capas de Internet, transporte y aplicación pueden funcionar de la misma manera sin importar cómo se conecte el dispositivo en el que se ejecutan.

Así, por ejemplo, tu navegador web no necesita saber si se está ejecutando en un dispositivo con conexión inalámbrica o a través de un par trenzado. Solo necesita las capas subyacentes para enviar y recibir datos.

Al final de esta lección, podrás explicar qué son las direcciones MAC y cómo se las usa para identificar computadoras. También sabrás describir los diversos componentes que forman una trama de Ethernet. Y podrás diferenciar entre direcciones de unidifusión, multidifusión y difusión. Por último, podrás explicar cómo las verificaciones de redundancia cíclica garantizan la integridad de los datos enviados por Ethernet. Comprender estos conceptos te ayudará a solucionar una variedad de problemas como especialista en soporte de TI.

Advertencia: estás por recibir una lección de tecnología a la vieja usanza. Aquí va.

## Ethernet

Ethernet es una tecnología bastante antigua. Nació en 1980 y su primera estandarización bien acabada vio la luz en 1983. Desde entonces, se introdujeron algunos cambios, principalmente para respaldar la necesidad cada vez mayor de ancho de banda. En su mayor parte, sin embargo, lo que usamos de Ethernet actualmente es comparable a los estándares de Ethernet tal como se publicaron por primera vez, años atrás.

En 1983, las redes de computadoras eran totalmente diferentes a las de hoy. Una de las diferencias notables en la topología LAN era que el conmutador o concentrador conmutable no se había inventado aún. Esto implicaba que, con frecuencia, muchos o todos los dispositivos en una red compartieran un único dominio de colisión.

Tal vez recuerdes, de lo que hablamos sobre concentradores y conmutadores, que un dominio de colisión es un segmento de red en el que solo un dispositivo a la vez puede comunicarse. Esto se debe a que todos los datos en un dominio de colisión se envían a todos los nodos conectados a él. Si dos computadoras enviaran datos a través del cable al mismo tiempo, esto daría lugar a colisiones literales de la corriente eléctrica que representa nuestros unos y ceros, y su resultado final sería algo ininteligible.

Ethernet, como protocolo, resolvió este problema mediante el uso de una técnica conocida como acceso múltiple con detección de portadora y detección de colisión. No es fácil de pronunciar. Generalmente lo abreviamos así: CSMA/CD. CSMA/CD se usa para determinar cuándo los canales de comunicación están despejados y el dispositivo está libre para transmitir datos.

La forma en que CSMA/CD funciona es bastante simple: si no hay datos en transmisión actual en el segmento de red, un nodo se sentirá libre de enviar datos. Si resulta que dos o más computadoras intentar enviar datos al mismo tiempo, las computadoras detectan esta colisión y dejan de hacerlo. Luego, cada dispositivo involucrado en la colisión espera durante un intervalo aleatorio de tiempo antes de intentar enviar datos de nuevo. Este intervalo aleatorio ayuda a prevenir que todas las computadoras involucradas en la colisión vuelvan a colisionar la próxima vez que intenten transmitir algo.

Cuando un segmento de red es un dominio de colisión, todos los dispositivos ubicados en ese segmento reciben todas las comunicaciones de todo el segmento, lo que implica que necesitamos una manera de identificar a qué nodo estaba destinada la transmisión. Aquí es donde entra en juego algo conocido como dirección de control de acceso a medios, o dirección MAC.

Una dirección MAC es un identificador único global acoplado a una interfaz de red individual. Es un número de 48 bits representado generalmente por seis grupos de dos números hexadecimales. Así como la notación binaria es una forma de representar números con solo dos dígitos, la notación hexadecimal es una forma de representar números usando 16 dígitos. Como no tenemos números para representar ningún dígito individual superior a nueve, los números hexadecimales emplean las letras A, B, C, D, E y F para representar los números 10, 11, 12, 13, 14 y 15.

Octeto es otra forma de llamar a cada grupo de números en una dirección MAC. Un octeto, en redes informáticas, es cualquier número que se pueda representar con 8 bits. En este caso, dos dígitos hexadecimales pueden representar los mismos números que 8 bits.

Quizás notaste que mencionamos que las direcciones MAC son globalmente únicas, lo que podría haberte dejado con la duda de cómo sería eso posible. La respuesta corta es que un número de 48 bits es mucho más grande de lo que cabría esperar. El número total de posibles direcciones MAC que podrían existir es 2 a la potencia 48, es decir, 281,474,976,710,656 posibilidades únicas. Eso es un montón de posibilidades.

Una dirección MAC se divide en dos secciones. Los primeros tres octetos de una dirección MAC se conocen como Identificador único de organización (OUI). Son asignados a fabricantes de hardware individuales por el IEEE, o Instituto de Ingenieros Eléctricos y Electrónicos. Esta es información útil para recordar porque significa que siempre puedes identificar al fabricante de una interfaz de red por su dirección MAC.

Los últimos tres octetos de la dirección MAC pueden asignarse de cualquier forma que el fabricante quiera con la condición de que solo asigne cada dirección posible una sola vez para que todas las direcciones MAC sigan siendo globalmente exclusivas.

Ethernet utiliza direcciones MAC para garantizar que los datos que envía tengan una dirección para la máquina que envió la transmisión y otra dirección para la que debía recibir esa transmisión. De esta manera, incluso en un segmento de red que actúa como un dominio de colisión simple, cada nodo en esa red sabe cuándo el tráfico está destinado para sí.

