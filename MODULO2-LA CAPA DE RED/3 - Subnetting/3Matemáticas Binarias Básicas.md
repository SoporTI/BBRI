Los números binarios pueden parecer intimidantes al principio, ya que se ven tan diferentes de los números decimales. Pero, en lo que respecta a lo básico, la matemática subyacente a contar, sumar o restar números binarios es exactamente la misma que con los números decimales.

Es importante señalar que no hay diferentes tipos de números. Los números son universales. Sólo hay diferentes notaciones para hacer referencia a ellos. Los humanos, muy probablemente porque casi todos tenemos diez dedos en las manos y otros diez en los pies, decidimos usar un sistema con diez cifras individuales para representar todos los números. Las cifras 0, 1, 2, 3, 4, 5, 6, 7, 8 y 9 se pueden combinar de diversas maneras para representar cualquier número entero que exista.

Como en total hay diez cifras en uso en un sistema decimal, otra forma de referirnos a él es sistema numeral de base 10.

Debido a restricciones de funcionamiento de las puertas lógicas dentro de un procesador, es mucho más fácil para las computadoras pensar las cosas solo en términos de 0 y 1. Esto también se conoce como sistema binario o de base 2.

Puedes representar todos los números enteros en binario de la misma forma que puedes hacerlo en decimal, solo se ve un poco diferente.

Cuando cuentas en decimal, te mueves por las cifras en forma ascendente hasta que se agotan, entonces agregas una segunda columna de mayor importancia. Empecemos a contar desde 0 hasta llegar a 9. Una vez que llegamos a 9, básicamente empezamos de nuevo, agregamos un 1 a una nueva columna, luego comienzas de nuevo desde 0 en la columna original. Repetimos este proceso una y otra vez para contar todos los números enteros.

Contar en binario es exactamente lo mismo, solo que tienes dos cifras disponibles. Empiezas en 0, que es el mismo 0 que en decimal. Luego aumentas una vez. Ahora tienes un 1, que es el mismo 1 que en decimal. Como nos quedamos sin cifras para usar, es momento de agregar una nueva columna. Así que ahora tenemos el número 10, que es lo mismo que 2 en decimal. 11 es 3, 100 es 4, 101 es 5, 110 es 6, 111 es 7, etc. Es exactamente lo mismo que hacemos con el sistema decimal, solo con menos cifras a nuestra disposición.

Al trabajar con diversas tecnologías informáticas, a menudo te encontrarás con el concepto de bits, o unos y ceros. Hay un truco bastante simple para descubrir cuántos números decimales pueden representarse con un cierto número de bits. Si tienes un número de ocho bits, puedes calcular dos a la octava (2Λ8), esto te da 256, lo que te permite saber que un número de ocho bits puede representar 256 números decimales, o dicho de otra manera, los números del 0 al 255. Un número de 4 bits sería dos a la cuarta (2Λ4), o 16 números totales. Un número de 16 bits sería dos a la potencia de dieciséis (2Λ16) o 65,536 números.

Para vincular esto a lo que ya sabes, este truco no solo funciona para el sistema binario, sino también para cualquier sistema numérico: tan solo cambia la base. Puedes recordar que también podemos referirnos a binario como base 2 y decimal como base 10. Todo lo que tienes que hacer es cambiar la base que estás elevando a una potencia por el número de columnas.

Por ejemplo, tomemos un número de base 10 con dos columnas de dígitos. Esto se traduciría en 10 al cuadrado (10Λ2), 10 al cuadrado es igual a 100, que es exactamente la cantidad de números que puedes representar con dos columnas de dígitos decimales, es decir, los números 0 a 99. De manera similar, 10 al cubo (10Λ3) es 1,000, que es exactamente la cantidad de números que puedes representar con tres columnas de dígitos decimales, es decir, los números del 0 al 999.

No solo contar en bases diferentes es igual, las operaciones aritméticas simples como la suma también lo son. De hecho, la suma binaria es incluso más simple que en cualquier otra base, ya que solo tienes cuatro situaciones posibles. 0 + 0 = 0, al igual que en decimal. 0 + 1 = 1, y 1 + 0 = 1, también deberían parecerte familiares. 1 + 1 = 10, se ve un poco diferente, pero aún así debería tener sentido. Llevaste el dígito a la siguiente columna una vez que llegaste a 10 en la suma decimal, lleva un dígito a la siguiente columna una vez que llegues a 2 en la suma binaria.

La suma es lo que se conoce como un operador y hay muchos operadores que las computadoras usan para hacer cálculos. Dos de los operadores más importantes son OR y AND. En lógica computacional, un 1 representa verdadero y un 0 representa falso. La forma en que trabaja el operador es observar cada dígito, y si alguno de ellos es verdadero, el resultado es verdadero. La ecuación básica es X OR Y = Z. Que podría leerse como "si X o Y son verdaderos, entonces Z es verdadero; de lo contrario, es falso". Por lo tanto, 1 OR 0 = 1, pero 0 OR 0 = 0.

El operador AND funciona como suena: devuelve "verdadero" si ambos valores son verdaderos. Por lo tanto, 1 AND 1 = 1, pero 1 AND 0 = 0 y 0 AND 0 = 0, y así sucesivamente.

Ahora, tal vez te preguntes por qué hemos visto todo esto. No, no es para confundirte. Todo es para que nos ayude a explicarte un poco más las máscaras de subred. Una máscara de subred es una forma en que una computadora puede usar operadores AND para determinar si existe una dirección IP en la misma red. Esto significa que la porción de ID del host también se conoce porque será todo lo que sobre.

Usemos la representación binaria de nuestra dirección IP favorita, 9.100.100.100, y nuestra máscara de subred favorita, 255.255.255.0. Una vez que coloques una encima de la otra y apliques un operador AND binario en cada columna, notarás que el resultado es la porción de ID de red y de ID de subred de nuestra dirección IP, o 9.100.100.

La computadora que acaba de realizar esta operación ahora puede comparar los resultados con su propia ID de red para determinar si la dirección está en la misma red o en otra diferente. Apuesto a que nunca pensaste que tendrías una dirección IP o de subred favorita, pero eso es lo que sucede en el maravilloso mundo de las matemáticas binarias básicas.
