> [!TIP]  
> [Ver video](https://youtu.be/-dSIn6kpDvw)

En un momento dado, trabajaba para un **proveedor de servicios gestionados**, que es básicamente una empresa que proporciona soporte de TI para otras empresas. Y estábamos ayudando a uno de nuestros clientes a migrar algunos de sus sistemas a una nueva versión, y cada vez que trataba de iniciar uno de sus servicios, daba un error y se bloqueaba, y el kernel se volcaba en la pantalla, y no podíamos descubrir por qué. 

Finalmente, recibimos apoyo de la empresa que realmente escribe este software, y ellos no pueden resolverlo y eso escala y escala, y al final, tengo el número de teléfono personal del vicepresidente de esta empresa, que es la persona que escribió el software por primera vez. Él y yo pasamos varios días tratando de averiguar lo que sucedía, sin resultado alguno.

Intentamos ejecutar esto en diferentes servidores. Probamos todo lo que se nos ocurrió hasta que me di cuenta de que la clave de licencia que había que implementar para que el software funcionara, había sido copiada de una máquina con Windows a una máquina con Linux, lo que significa que los caracteres de final de línea que indican que la línea terminó, "Vaya a la siguiente línea", eran diferentes. Este software se atascaba con este carácter de salto de línea diferente.

Todo lo que tuve que hacer fue ejecutar un comando y cambiarlo a un formato de archivo de Linux, y todo funcionó. Perdí dos semanas de mi vida, pero pudimos seguir adelante.
