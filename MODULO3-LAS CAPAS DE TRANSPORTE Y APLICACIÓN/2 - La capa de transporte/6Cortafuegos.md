> [!TIP]  
> [Ver video](https://youtu.be/CwYHozSHNTw)

¿Conoces cuál es el dispositivo de red del que todavía no hemos hablado y con el que probablemente estés muy familiarizado? El **firewall**. Un firewall es un dispositivo que bloquea el tráfico que cumple ciertos criterios. Los firewalls son un concepto fundamental para mantener la seguridad en una red ya que son la principal forma en la que puedes detener el tráfico que no quieres que ingrese a una red.

Los firewalls pueden funcionar en muchas capas diferentes de la red. Hay firewalls que pueden inspeccionar el tráfico de la capa de aplicación, y firewalls cuya tarea principal es bloquear rangos de direcciones IP. La razón por la que veremos los firewalls aquí es que se los usa comúnmente en la capa de transporte.

Los firewalls que trabajan en la capa de transporte tendrán, por lo general, una configuración que les permite bloquear el tráfico dirigido a ciertos puertos, a la vez que permite el tráfico a otros puertos. Imaginemos la red de una pequeña empresa. Esta pequeña empresa podría tener un servidor que aloja múltiples servicios de red. Este servidor podría tener un servidor web que aloja el sitio web de la empresa, y que además funciona como servidor de archivos para documentos internos confidenciales.

Un firewall colocado en el perímetro de la red podría configurarse para permitir que cualquiera envíe tráfico al puerto 80 para ver la página web. Al mismo tiempo, podría bloquear todo el acceso para IP externas a cualquier otro puerto, para que nadie fuera de la red de área local pueda acceder al servidor de archivos.

Los firewalls, a veces, son dispositivos de red independientes, pero es mejor pensar en ellos como un programa que puede ejecutarse en cualquier lugar. Para muchos usuarios de empresas y casi todos los usuarios hogareños, la funcionalidad de un router y de un firewall la lleva a cabo el mismo dispositivo. Y los firewalls pueden funcionar en hosts individuales en lugar de ser un dispositivo de red. Todos los principales sistemas operativos modernos tienen funcionalidad de firewall incorporada. De esa manera, bloquear o permitir el tráfico a diversos puertos y, por lo tanto, a servicios específicos también puede hacerse a nivel del host.

A continuación, pon en marcha tu cerebro para un breve cuestionario.
