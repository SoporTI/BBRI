Hemos visto cómo los servidores de nombres autoritativos son responsables de responder a las solicitudes de resolución de nombres para dominios específicos, pero hacen más que eso. Un servidor de nombres autoritativo es en verdad responsable de una zona DNS específica.

Las zonas DNS son un concepto jerárquico. Los servidores de nombres raíz que vimos anteriormente son responsables de la zona raíz. Cada servidor de nombres TLD es responsable de la zona que cubre su TLD específico, y lo que llamamos servidores de nombres autoritativos son responsables de algunas zonas subyacentes aún más detalladas. Los servidores de nombres raíz y TLD también son en realidad servidores de nombres autoritativos. Es solo que las zonas para las que están acreditados son casos especiales.

Debo señalar que las zonas no se superponen. Por ejemplo, la autoridad administrativa del servidor de nombres TLD para el TLD ".com" no abarca el dominio google.com. En cambio, finaliza en el servidor autoritativo responsable de google.com.

El propósito de las zonas DNS es permitir un control más sencillo sobre múltiples niveles de un dominio. A medida que aumenta el número de registros de recursos en un solo dominio, se vuelve un dolor de cabeza administrarlos a todos. Los administradores de red pueden aliviar este dolor dividiendo sus configuraciones en múltiples zonas.

Imaginemos una gran empresa propietaria del dominio largecompany.com. Esta empresa tiene oficinas en Los Ángeles, París y Shanghái, muy cosmopolita. Digamos que cada oficina tiene alrededor de 200 personas con su propio equipo de escritorio con un nombre único. Estos serían 600 registros A para rastrear si todo estuviera configurado como una sola zona.

Lo que la empresa podría hacer, en cambio, es dividir cada oficina en su propia zona. Ahora, podríamos tener la.largecompany.com, pa.largecompany.com y sh.largecompany.com como subdominios, cada uno con sus propias zonas DNS. Ahora se necesitaría un total de cuatro servidores de nombres autoritativos para la configuración, uno para largecompany.com y uno para cada uno de los subdominios.

Las zonas se configuran a través de lo que se conoce como archivos de zona, archivos de configuración simple que declaran todos los registros de recursos para una zona en particular. Así que un archivo de zona tiene que contener una SOA, o declaración de registro de recursos de inicio de autoridad. Este registro SOA declara la zona y el nombre del servidor de nombres que tiene autoridad en ella. Junto con el registro SOA, por lo general encontrarás registros NS que indican otros servidores de nombres que también pueden ser responsables de esta zona.

Para simplificar, nos hemos referido a "servidor" en singular al analizar lo que es responsable de su zona, ya sea a nivel de raíz, TLD o dominio, pero a menudo van a haber múltiples servidores físicos con sus propios FQDN y direcciones IP involucradas. Tener varios servidores implementados para algo tan importante como DNS es bastante común. ¿Por qué? Bueno, si un servidor tuviera un problema o sufriera una falla de hardware, siempre puede confiar en uno de los otros para entregar el tráfico DNS.

Además de los registros SOA y NS, también encontrarás algunos o todos los demás tipos de registro de recursos que ya hemos visto, como A, Quad A y CNAME, junto con configuraciones como valores TTL predeterminados para los registros entregados por esta zona.

Así como los subdominios pueden tener muchas, muchas capas de profundidad, las zonas también se pueden configurar para hacer esto, pero al igual que con los subdominios, es raro ver zonas que vayan más allá de unos pocos niveles.

A veces, también verás lo que se conoce como archivos de zona de búsqueda inversa. Estos permiten a los agentes de resolución de DNS solicitar una IP y obtener el FQDN asociado a ella. Estos archivos son los mismos que los archivos de zona, salvo que en lugar de los registros A y Quad A, que resuelven nombres a direcciones IP, encontrarás principalmente declaraciones de registro de recursos de puntero. Como supones, un PTR o registro de puntero, resuelve una IP a un nombre.

A continuación, un cuestionario dinámico para ti, antes de una nueva lección dinámica sobre el Protocolo de configuración dinámica de host. Nos vemos.