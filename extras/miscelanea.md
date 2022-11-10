# Resumen de Conceptos varios de Python

## Creación de Módulos y Paquetes en Python.
* Bibliografia de la web [UniWebSidad - Creacion Modulos](https://uniwebsidad.com/libros/python/capitulo-3/creando-modulos-empaquetados)
* [CodigoFuente.org](https://www.codigofuente.org/crear-e-importar-modulos-python/)


### Creando módulos empaquetados
En Python, cada uno de nuestros archivos `.py` se denominan **módulos**. Estos módulos, a la vez, pueden formar parte de **paquetes**.

Un **paquete**, es una **carpeta** que contiene archivos `.py`. Pero, para que una carpeta pueda ser considerada un paquete, debe contener un archivo 
de inicio llamado `__init__.py`. Este archivo, no necesita contener ninguna instrucción. De hecho, puede estar completamente vacío.

Los paquetes, a la vez, también pueden contener otros sub-paquetes:

Y los módulos, no necesariamente, deben pertenecer a un paquete:

### Importando módulos enteros

El contenido de cada módulo, podrá ser utilizado a la vez, por otros módulos. Para ello, es necesario importar los módulos que se quieran utilizar. 
Para **importar un módulo**, se utiliza la instrucción `import`, seguida del **nombre del paquete** (si aplica) más el nombre del módulo (sin el .py) 
que se desee importar.

Cuando el intérprete encuentra una declaración de importación, **importa el módulo** si el módulo está presente en la **ruta de búsqueda**. 
Una ruta de búsqueda es una **lista de directorio**s que el intérprete busca antes de importar un módulo. Por ejemplo, para importar el módulo support.py, debe colocar el siguiente comando en la parte superior de la secuencia de comandos:

`#!/usr/bin/python`

`# Importar modulo support`
`import support`
 Ahora se puede llamar a la siguiente funcion del paquete **support**
`support.print_func ("Sara")`



Ejemplo:

`# -*- coding: utf-8 *-*`

`#!/usr/bin/python`

`import modulo`          # importar un módulo que no pertenece a un paquete

`import paquete.modulo1` # importar un módulo que está dentro de un paquete

`import paquete.subpaquete.modulo1`

La instrucción `import` seguida de `nombre_del_paquete.nombre_del_modulo`, nos permitirá hacer uso de todo el código que dicho módulo contenga.

> Nota
> Python tiene sus propios módulos, los cuales forman parte de su librería de módulos estándar, que también pueden ser importados.

### Namespaces

Para acceder (desde el módulo donde se realizó la importación), a cualquier elemento del módulo importado, se realiza mediante el **namespace**, 
seguido de un punto (.) y el nombre del elemento que se desee obtener. En Python, un **namespace**, es el nombre que se ha indicado luego 
de la palabra import, es decir la ruta (namespace) del módulo:

`print(modulo.CONSTANTE_1)`
`print(paquete.modulo1.CONSTANTE_1)`
`print(paquete.subpaquete.modulo1.CONSTANTE_1)`

### Alias
Es posible también, abreviar los namespaces mediante un **alias**. Para ello, durante la importación, se asigna la palabra clave `as` seguida del alias 
con el cuál nos referiremos en el futuro a ese namespace importado:

`import modulo as m`
`import paquete.modulo1 as pm`
`import paquete.subpaquete.modulo1 as psm`

Luego, para acceder a cualquier elemento de los módulos importados, el namespace utilizado será el alias indicado durante la importación:

`print m.CONSTANTE _1`
`print pm.CONSTANTE _1`
`print psm.CONSTANTE_1`

### Importar módulos sin utilizar namespaces
En Python, es posible también, importar de un módulo solo los elementos que se desee utilizar. 
Para ello se utiliza la instrucción `from` seguida del `namespace`, más la instrucción `import` seguida del elemento que se desee importar:

`from paquete.modulo1 import CONSTANTE_1`

En este caso, se accederá directamente al elemento, sin recurrir a su namespace:

`print(CONSTANTE_1)`

Es posible también, importar más de un elemento en la misma instrucción. Para ello, cada elemento irá separado por una coma (,) y un espacio en blanco:

`from paquete.modulo1 import CONSTANTE_1, CONSTANTE_2`

>Nota: importación
La importación de módulos debe realizarse al comienzo del documento, en orden alfabético de paquetes y módulos.
Primero deben importarse los módulos propios de Python. Luego, los módulos de terceros y finalmente, los módulos propios de la aplicación.
Entre cada bloque de imports, debe dejarse una línea en blanco.

### Búsqueda de módulos
Cuando importa un módulo, el intérprete de Python busca el módulo en las siguientes secuencias:

1. El directorio actual.
1. Si no se encuentra el módulo, Python busca cada directorio en la variable de shell **PYTHONPATH**.
1. Si todo lo demás falla, Python comprueba la ruta predeterminada. En UNIX, esta ruta predeterminada es normalmente `/usr/local/lib/python/`.

La ruta de búsqueda del módulo se almacena en el módulo del sistema **sys** como la variable **sys.path**. La variable sys.path contiene el directorio actual, PYTHONPATH y el valor predeterminado dependiente de la instalación.

La variable **PYTHONPATH**

PYTHONPATH es una variable de entorno, que consiste en una lista de directorios. La sintaxis de PYTHONPATH es la misma que la de la variable de shell PATH.

Aquí hay una típica PYTHONPATH de un sistema Windows – `set PYTHONPATH = c:\python20\lib`
o para linux
`set PYTHONPATH =/usr/local/lib/python`

-------
