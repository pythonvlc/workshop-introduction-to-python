===============================
Taller de Introducción a Python
===============================

El objetivo de este taller es ofrecer una pequeña introducción práctica
a todos aquellos que no conozcan Python y quieran iniciarse en este
lenguaje de programación.

Forma de trabajar
-----------------

* Se realizarán grupos de 3 personas siempre que sea posible, intentando que
aquellos que tengan más conocimientos se junten con los que tengan poco o
ninguno.

* El trabajo se dividirá en iteraciones, donde en cada una de ellas el
grupo tratara de resolver un pequeño poblema, que será más complejo
conforme avancen las iteraciones.

Iteración #0: Instalación de Python 3
-------------------------------------

**Desde el código fuente**

.. code-block:: console

    $ wget https://www.python.org/ftp/python/3.5.2/Python-3.5.2.tgz
    $ tar xf Python-3.5.2.tgz
    $ cd Python-3.5.2
    $ ./configure
    $ make
    $ sudo make install


**macOS**

Usando `Homebrew <http://brew.sh/>`_

.. code-block:: console

    $ brew install python3

Comprobar que funciona correctamente:

.. code-block:: console

    $ python
    Python 3.5.2 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>

Iteración #1: Hello world
-------------------------

Desde el propio intérprete:

.. code-block:: python

    >>> print("Hello world!")

Desde un fichero, por ejemplo ``hello.py``, con el siguiente contenido:

.. code-block:: python

    print("Hello world!")

Lo ejecutamos:

.. code-block:: console

    $ python hello.py
    Hello world!

Iteración #2: Creación de un virtualenv
---------------------------------------

Usando el módulo ``venv`` de Python 3:

.. code-block:: console

    $ python -m venv myvenv

Usando el paquete ``virtualenvwrapper``:

.. code-block:: console

    $ sudo pip install virtualenv virtualenvwrapper

Para que funcione correctamente hay que añadir lo siguiente al fichero
``.bashrc``:

.. code-block:: bash

    export WORKON_HOME=$HOME/.virtualenvs
    source /usr/bin/virtualenvwrapper.sh

Y lo recargamos ``.bashrc``:

.. code-block:: console

    $ source ~/.bashrc

Ahora podemos usar el comando ``mkvirtualenv`` para crear el viertualenv

.. code-block:: bash

    $ mkvirtualenv myvenv
    (myvenv) $

Iteración #4: Números
---------------------


Iteración #5: Variables
-----------------------


Iteración #6: Cadenas de texto
------------------------------

.. code-block:: python

    >>> text = "¡Bienvendio a Python!"
    >>> other_text = 'Con comillas simples y comillas dobles funciona igual'
    >>> long_text = '''Usando tres comillas simples se pueden
    hacer cadenas de más de una línea.'''

.. code-block:: python

    >>> name = "Antonio"
    >>> text = "Hola %s!" % name
    >>> other_text = "¿Qué te trae por aquí, {}?".format(name)
    >>> more_options = "Con esto puedes " + "concatenar cadenas"
