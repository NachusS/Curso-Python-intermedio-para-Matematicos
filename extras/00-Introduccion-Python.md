# El Lenguaje de programación Python

## ¿Qué es Python?

[Python](http://www.python.org/) es un lenguaje de programación moderno, _de propósito general_, _orientado al objeto_ y de _alto nivel_. Fue creado por [Guido van Rossum](http://es.wikipedia.org/wiki/Guido_van_Rossum), conocido como el BDFL ("Benevolent Dictator for Life", es decir "Dictador Benevolente Vitalicio" del proyecto Python). La primera versión (0.9.0) de Python fue lanzada en 1991, y la versión 1.0 en 1994.

<img src="http://upload.wikimedia.org/wikipedia/commons/thumb/6/66/Guido_van_Rossum_OSCON_2006.jpg/400px-Guido_van_Rossum_OSCON_2006.jpg" width="150">

**Algunos de los principios bajo los que está concebido el lenguaje (Tim Peters, "El Zen de Python") son:**

* Bello es mejor que feo.
* Explícito es mejor que implícito.
* Simple es mejor que complejo.
* Complejo es mejor que complicado.
* La legibilidad cuenta.
* Los casos especiales no son tan especiales como para quebrantar las reglas.

**Características generales de Python:**

* Lenguaje **fácil de aprender**.
* Lenguaje **versátil** en su utilización.
* **Lenguaje limpio y simple:** Código fácil de leer e intuitivo, sintaxis minimalista y fácil de aprender. Su mantención escala bien con el tamaño de los proyectos.
* Incorpora una colección de **herramienta básicas** para el tratamiento y visualización de datos.
* Suministra un "entorno" **unificado** e **interactivo**.
* Requiere un tiempo de desarrollo **reducido** y un tiempo de ejecución **razonable**.

**Detalles técnicos:**

* **Tipado dinámico:** No se necesita definir el tipo de las variables, argumentos de funciones, ni tipos de retorno.
* **Manejo de memoria automático:** No se necesita reservar explícitamente memoria para las variables y los arreglos de datos. Sin bugs de fuga de memoria. 
* **Interpretado:** No se requiere compilar el código. El intérprete Python lee y ejecuta el código python directamente.

**Ventajas de Python:**

* La principal ventaja es la facilidad de programar, minimizando el tiempo requerido para desarrollar, depurar y mantener el código.
* Lenguaje bien diseñado que fomenta muchas buenas prácticas de programación:
 * Programación modular y orientada al objeto, buen sistema para empaquetar y reusar código. Esto a menudo resulta en un código más transparente, mantenible, y libre de bugs.
 * Documentación estréchamente integrada al código.
* Un gran librería estandar, y una gran colección de paquetes externos.

**Desventajas de Python:**

* Como Python es un lenguaje interpretado y de tipado dinámico, la ejecución de código python puede ser lenta comparada con lenguajes compilados y de tipado estático, tales como C y Fortran. 
* Algo descentralizado, con diferentes ambientes, paquetes y documentación diseminada en distintos lugares. Esto puede hacer difícil el comienzo.

### Python versus Matlab

**Ventajas de Matlab**:

* Múltiples bibliotecas con numerosos algoritmos para la resolución de diferentes problemas.
* Una rápida ejecución debido a que las bibliotecas están, normalmente, escritas en un lenguaje compilado.
* Un entorno de desarrollo *agradable* y funcional.
* Soporte comercial disponible.

**Desventajas de Matlab**:

* El lenguaje de base puede ser *restrictivo* para usuarios avanzados. No hay acceso al código fuente.
* "Show me the money..."

### Python versus lenguajes compilados (Fortran, C, C++)

**Ventajas de Fortran, C, C++**:

* Rápidos.
* Compiladores **super** optimizados.
* Bibliotecas científicas **super** optimizadas (desde antaño).

**Desventajas de Fortan, C, C++**:

* No hay interactividad durante el desarrollo (necesariamente, hay un paso de compilación).
* Sintaxis compleja.
* Manejo manual de la memoria.

## ¿Qué hace a Python adecuado para la Computación Científica?

<!-- offline version <img src="files/images/optimizing-what.png" width="300"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/optimizing-what.png" width="600">

* Python tiene una posición fuerte en la computación científica: 
    * Gran comunidad de usuarios. Es fácil encontrar ayuda y documentación.

* Extenso ecosistema de librerías científicas y entornos
    * [Numpy](https://numpy.org/): Python Numérico.
    * [Pandas](https://pandas.pydata.org/): Hrrramienta de manejo y gestión de datos.
    * [Scipy](http://www.scipy.org):  Python Científico.
    * [Matplotlib](http://www.matplotlib.org): Librerías Gráficas.

* Gran desempeño debido a la gran integración con códigos altamente testeados y optimizados escritos en C y Fortran:
    * blas, atlas blas, lapack, arpack, Intel MKL, ...

* Buen soporte para:
    * Procesamiento en paralelo.
    * Comunicación entre procesos (Interprocess communication, MPI).
    * Cálculo con GPU (OpenCL y CUDA).
* Disponible y apropiado para uso con cluster de cálculo de alto desempeño (high-performance computing clusters). 
* ¡Sin costos de licencia y de código abierto!.
* Creciente y pujante comunidad apoyando el desarrollo y evolución del lenguaje.

**Desventajas**:

* Un entorno de desarrollo menos *agradable* comparado con Matlab (**totalmente discutible...**. **Esto está cambiando rápidamente gracias a los [Jupyter Notebooks](https://jupyter.org/)**). 
* Algunos algoritmos especializados todavía no se han desarrollado (**pero no falta mucho...**).
* Relativamente lento... (**varias soluciones disponibles y en desarrollo**).

### La estructura de datos (pila) de Python Científico

<!-- <img src="files/images/scientific-python-stack.png" width="300"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/scientific-python-stack.png" width="300">

## Entornos Python

Python no es sólo un lenguaje de programación, sino que también la implementación estándar del *intérprete* (técnicamente llamado [CPython](http://es.wikipedia.org/wiki/CPython)) que realmente ejecuta el código Python en un computador.

Existen también muchos entornos distintos a través de los cuales se puede usar el intérprete Python. Cada entorno tiene distintas ventajas y es adecuado para diferentes rutinas de trabajo. Una fortaleza de Python es que es versátil y puede ser usado de formas complementarias, pero esto puede ser confuso para principiantes, por lo que comenzaremos con un breve vistazo de los entornos Python útiles en computación científica.

### Intérprete Python

La forma estándar de usar el lenguaje de programación Python es usar el intérprete Python para ejecutar código Python. El intérprete Python es un programa que lee y ejecuta el código Python en archivos, que son pasados como argumentos. En la consola de comandos, el comando ``python`` se usa para invocar al intérprete Python.

Por ejemplo, para ejecutar un archivo ``mi-programa.py``, que contiene código Python, desde la consola de comandos, use:

    $ python mi-programa.py

Podemos también iniciar el intérprete simplemente escribiendo ``python`` en la consola, y escribiendo interactivamente código en el intérprete. 

<!-- <img src="files/images/python-screenshot.jpg" width="600"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/python-screenshot.png" width="600">


Ésta es la forma en que a menudo deseamos trabajar desarrollando aplicaciones científicas, o cuando se realizan pequeños cálculos. Sin embargo, el intérprete Python estándar no es muy conveniente para este tipo de trabajo, debido a múltiples limitaciones.

### IPython

[IPython](http://ipython.org/) es una shell (intérprete de comandos) interactiva que resuelve muchas de las limitaciones del intérprete de Python estándar, y es una poderosa heramienta para uso científico de Python. IPython suministra una prompt interactiva, y mucho más amigable al usuario, del intérprete Python. IPython fue creado por [Fernando Perez](http://fperez.org/) en 2001.

<!-- <img src="http://fperez.org/_static/fperez_headshot_lg.jpg" width="150"> -->

Una instancia de IPython corriendo en una consola luce así:

<!-- <img src="files/images/ipython-screenshot.png" width="600"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/ipython-screenshot.png" width="600">

Algunas de las características más útiles de IPython son:

* Historial de comandos, que puede ser navegado con las teclas de flechas hacia arriba y abajo.
* Autocompletación de tabs.
* Edición de código en línea.
* Introspección de objetos, y extracción automática de cadenas de documentación a partir de objetos Python como clases y funciones.
* Buena interacción con la línea de comandos del sistema operativo.
* Soporte de múltiples procesos paralelos back-end, que pueden ejecutarse en cluster computacionales o en servicios en la nube como Amazon EE2.

## Spyder

[Spyder](http://code.google.com/p/spyderlib/) es un IDE (entorno de desarrollo interactivo, por su sigla en inglés) similar a MATLAB para computación científica con Python. Tiene muchas de las ventajas de un IDE, como por ejemplo que todo, desde la edición del código, su ejecución y depuración, es realizado en un mismo entorno, y el trabajo de diferentes cálculos puede ser organizado como proyectos en el IDE.

<!-- <img src="files/images/spyder-screenshot.jpg" width="800"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/spyder-screenshot.jpg" width="800">

Algunas ventajas de Spyder:

* Poderoso editor de código, con coloreado de sintaxis, introspección dinámica de código, e integración con el depurador de Python.
* Explorador de variables, prompt de comando IPython.
* Documentación y ayuda integrada.

## Jupyter (IPython) notebook

[Jupyter notebook](https://jupyter.org/) es un entorno "de cuaderno'' basado en HTML para Python, similar a Mathematica o Maple. Originalmente estaba basado en la shell IPython, pero suministrando un ambiente basado en celdas con gran interactividad, donde los cálculos pueden ser organizados y documentados en una forma estructurada.

<!-- <img src="files/images/ipython-notebook-screenshot.png" width="800"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/ipython-notebook-screenshot.png" width="800">

Aunque se usa el navegador web con interfase gráfica, los notebooks IPython/Jupyter usualmente se ejecutan localmente, en el mismo computador que ejecuta el navegador. Para iniciar una nueva sesión de IPython notebook, ejecute el siguiente comando:

    $ jupyter notebook 
    
    $ jupyter lab

desde una carpeta en que que desea almacenar los cuadernos. Esto abrirá una nueva ventana del navegador (o una nueva pestaña en una ventana existente) con una página índice donde se muestran los cuadernos existentes y desde donde nuevos cuadernos pueden ser creados.

En el año 2014, los desarrolladores del Ipython Notebook decidieron crear el proyecto [Jupyter](http://jupyter.org/) que independiza la interfase del notebook del lenguaje de programación particular que se use (originalmente, Python). Esto permite usar las funcionalidades de interactividad de los notebooks con distintos lenguajes.

## Versiones de Python

Existen actualmente dos versiones de Python: Python 2 y Python 3. Python 3 eventualmente reemplazará a Python 2, pero no es 100% compatible con Python 2. Mucho del código Python existente ha sido escrito para Python 2, y aún es la versión más popular. En estas clases cualquiera de las dos versiones puede usarse, pero es probablemente más simple quedarse con Python 2 por ahora, ya que está más comúnmente disponible en paquetes precompilados e instaladores binarios.

Para ver qué versión de Python tiene, ejecute
    
    $ python --version
    Python 2.7.12
    
    $ python3 --version
    Python 3.4.0

Ultima versión:
    $ python3 --version
    Python 3.11.0

Es posible instalar varias versiones de Python en paralelo.

## Instalación

Existen diversas formas de instalar Python y sus distintos módulos. Una forma segura y simple de instalar y mantener estos paquetes es instalando una *distribución de Python*. 

Una distribución muy popular es [Anaconda](https://www.anaconda.com/distribution/), desarrollada y mantenida por la empresa [Anaconda, Inc.](https://www.anaconda.com) (previamente llamada "Continuum Analytics"). Puede descargar un archivo (~500 MB) con todos los paquetes requeridos para plataformas Linux, macOS y Windows desde https://www.anaconda.com/download, y realizar la instalación local siguiendo las instrucciones indicadas en el sitio.

## Presente y Futuro

* Python se ha convertido en un lenguaje muy popular para uso científico debido a la multiplicidad de herramientas que brinda, a la potencialidad en el perfeccionamiento de las mismas y la continua generación de nuevos módulos cada vez más especializados.

* Existen problemas que resolver y algunas cuestiones técnicas que desarrollar (no todo es color de rosa...).

* Sin embargo, las perspectivas son muy buenas, lo cual se ve reflejado no sólo en la proliferación de científicos que usan Python en su trabajo diario, sino también en la organización de conferencias específicas a nivel internacional ([SciPy](http://conference.scipy.org), [EuroSciPy](https://www.euroscipy.org/), [SciPyCon Argentina](http://scipycon.com.ar/), etc.) y en el aumento del número de publicaciones con código escrito en Python.

* Muchas empresas e industrias se valen de estas mismas herramientas para el desarrollo o análisis de sus procesos productivos.

# Introducción a la Computación Científica con Python

La Ciencia es dividida tradicionalmente en una rama experimental y una teórica, pero durante las últimas décadas la computación ha emergido como una parte muy importante de la Ciencia. La **computación científica** está a menudo muy relacionada con la teoría, pero posee también muchas características comunes con el trabajo experimental. Es por esto que a menudo es vista como una tercera rama de las ciencias. En muchos campos de la Ciencia, el trabajo computacional es un complemento importante tanto para el experimento como para la teoría, y actualmente una gran mayoría de las publicaciones experimentales y teóricas involucran cálculos numéricos, simulaciones y/o modelamiento computacional.

<center>
<!-- offline version <img src="files/images/teoria-experimento-computacion.png" width="300"> -->
<img src="https://raw.github.com/gfrubi/clases-python-cientifico/master/images/teoria-experimento-computacion.png" width="300">   
</center>

En las áreas experimentales y teóricas existen códigos de conducta bien establecidos referentes a cómo los resultados y métodos son publicados y puestos a disposición de otr@s científic@s. Por ejemplo, en las áreas teóricas, las derivaciones, demostraciones y otros resultados son publicados en detalle, o disponibles bajo solicitud. Similarmente, en el trabajo experimental, los métodos usados y los resultados son publicados, y todos los datos experimentales debiesen estar disponibles al ser solicitados. Se considera una práctica anticientífica el ocultar detalles cruciales de una prueba teórica o de un método experimental, que pudiesen impedir que otr@s científic@s reproduzcan los resultados.

En las ciencias computacionales no existen aún guías bien establecidas de cómo debiesen ser manejados el código fuente y los datos generados. Por ejemplo, es relativamente raro que el código fuente usado en simulaciones en artículos publicados sea puesto a disposición de los lectores, en contraste con la naturaleza abierta del trabajo experimental y teórico. Además, no es poco común que el código fuente del software de simulación sea reservado y considerado como una ventaja competitiva (o no necesario de ser publicado). 

Sin embargo, este punto a comenzado a atraer cada vez mayor atención, y algunas editoriales de revistas de alto nivel han hecho llamados a una mayor transparencia en las ciencias computacionales. Algunas revistas prestigiosas, incluyendo [Science](http://www.sciencemag.org/), han comenzado a requerir que los autores suministren a los lectores, luego de solicitarlo, el código fuente del software de simulación usado en las publicaciones. 

También se está discutiendo cómo facilitar la distribución de software científico, por ejemplo como material suplementario a los artículos científicos.

###  Referencias

 * [Reproducible Research in Computational Science](http://dx.doi.org/10.1126/science.1213847), Roger D. Peng, Science 334, 1226 (2011).

 * [Shining Light into Black Boxes](http://dx.doi.org/10.1126/science.1218263), A. Morin et al., Science 336, 159-160 (2012).
 
 * [The case for open computer programs](http://dx.doi.org/doi:10.1038/nature10836), D.C. Ince, Nature 482, 485 (2012).
 
 ## Requisitos para la Computación Científica

**Replicación** y **reproducibilidad** son dos pilares del método científico. Respecto al trabajo numérico, el satisfacer estos requerimientos implica las siguientes consideraciones prácticas:

* **Replicación**: Un(a) autor(a) de un artículo científico que involucra cálculos numéricos debería ser capaz de reproducir los resultados. 

* **Reproducibilidad**: Otr@s científic@s deberían ser capaces de realizar las mismas simulaciones numéricas y obtener los mismos resultados, dada la información acerca de los métodos usados en una publicación.


Para alcanzar estos objetivos, necesitamos:

* Mantener y documentar *exactamente* qué código fuente y qué versión fue usada para producir los datos y figuras en artículos publicados.

* Registrar información sobre qué versión de software externos ha sido usada. Mantener acceso al entorno que fue usado.

* Asegurarse que los códigos antiguos son respaldados y mantenidos para futura referencia. 

* Estar preparado para suministrar información adicional sobre los métodos usados, y tal vez adicionalmente los códigos de simulación, a un lector interesado que lo solicite (incluso años después que el artículo fue publicado!).

* Idealmente, los códigos deberían ser publicados en la red, para facilitar que otr@s científic@s interesad@s en el código puedan tener acceso a él.

### Herramientas para manejar código fuente

Asegurar la replicabilidad y la reproducibilidad de simulaciones científicas es un *problema complicado*, pero existen buenas herramientas que ayudan en esta tarea:

* Sistemas de Control de Revisión (Revision Control System, RCS). 
    * Algunas buenas opciones son:
        * git - http://git-scm.com.
        * mercurial - http://mercurial.selenic.com. También conocido como `hg`.
        * subversion - http://subversion.apache.org. También conocido como `svn`.

* Repositorios Online para código fuente. Disponibles tanto como repositorios públicos como privados. 
    * Algunas buenas alternativas son:
        * Github - https://github.com/
        * Bitbucket - http://www.bitbucket.com
        * Repositorios privados alojados en servidores de la Universidad.

**Notas**

> Los repositorios son además excelentes para controlar versiones de manuscritos, figuras, archivos de tesis, archivos de datos, bitácoras de laboratorio, etc. Básicamente para todo contenido digital que deba ser preservado y que es frecuentemente actualizado. Nuevamente, existen tanto repositorios públicos como privados. ¡Estas herramientas constituyen además muy buenas herramientas de colaboración!

## Material adicional

En Inglés:

 * [Python](http://www.python.org). El sitio oficial de Python.
 * [Think Python](http://www.greenteapress.com/thinkpython/). Un libro gratuito sobre Python.
 * [Pyvideo](http://pyvideo.org/). Colección de videos sobre Python (tutoriales, conferencias, etc.).

En Español:

 * [Tutorial de Python](http://docs.python.org.ar/tutorial/index.html). Traducción del tutorial oficial de Python, por Python Argentina.
 * [Python para Todos](http://mundogeek.net/tutorial-python/): Libro gratuito sobre Python, escrito por Raúl González Duque.
 * [Algoritmos y Programación 1](https://sites.google.com/site/fiuba7540rw/home/apunte_7540.pdf?attredirects=0): Apuntes de la asignatura "Algoritmos y Programación 1" de la Facultad de Ingeniería de la Universidad de Buenos Aires.
 * [Introducción a Python para científicos e ingenieros (2ª ed.)](https://www.youtube.com/playlist?list=PLoGFizEtm_6jCjWqRU8A-dQYQuo5q5KNc) Curso de introducción al lenguaje de programación Python enfocado principalmente a científicos, ingenieros o cualquier persona interesada en análisis y visualización de datos. Universidad de Alicante, impartido por Juan Luis Cano. Ver también [esta página](http://cacheme.org/curso-online-python-cientifico-ingenieros/) con información del curso.
 * [Python Argentina](http://python.org.ar/): Comunidad de Python en Argentina.
 * [Pybonacci](http://pybonacci.org/): Blog en español dedicado al uso científico de Python.
 
**Nota de autor original del Notebook:**

> Versión original en inglés de [J.R. Johansson](http://jrjohansson.github.io/) (robert@riken.jp).
También se han incluido elementos del tutorial de Damián Avila:  https://github.com/damianavila/Python-Cientifico-HCC
Traducido/Adaptado por [G.F. Rubilar](https://twitter.com/gfrubi).
La última versión de estos [Notebooks](http://ipython.org/notebook.html) está disponible en [http://github.com/gfrubi/clases-python-cientifico](http://github.com/gfrubi/clases-python-cientifico).
La última versión del original (en inglés) está disponible en [http://github.com/jrjohansson/scientific-python-lectures](http://github.com/jrjohansson/scientific-python-lectures).
Los otros notebooks de esta serie están listados en [https://jrjohansson.github.io/](https://jrjohansson.github.io/).

