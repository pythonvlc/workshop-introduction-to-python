===============================
Taller de Introducción a Python
===============================

El objetivo de este taller es ofrecer una pequeña introducción práctica
a todos aquellos que no conozcan Python y quieran iniciarse en este
lenguaje de programación.

Forma de trabajar
-----------------

* Se realizarán grupos de 3 personas siempre que sea posible, intentando que aquellos que tengan más conocimientos se junten con los que tengan poco o ninguno.

* El trabajo se dividirá en iteraciones, donde en cada una de ellas el grupo tratara de resolver un pequeño poblema, que será más complejo conforme avancen las iteraciones.

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

Aprendamos a usar Python como si de una calculadora se tratara.

* ``+`` suma
* ``-`` resta
* ``/`` división
* ``*`` multiplicación
* ``%`` módulo
* ``<`` menor que
* ``>`` mayor que
* ``<=`` menor o igual que
* ``>=`` mayor o igual que

Iteración #5: Variables
-----------------------

Guardemos nuestros cálculos, números y lo que queramos en un lugar donde no
se pierdan.

.. code-block:: python

    >>> cars = 100
    >>> space_in_a_car = 4.0
    >>> drivers = 30
    >>> passengers = 90
    >>> cars_not_driven = cars - drivers
    >>> cars_driven = drivers
    >>> carpool_capacity = cars_driven * space_in_a_car
    >>> average_passengers_per_car = passengers / cars_driven

Iteración #6: Cadenas de texto
------------------------------

No sólo se pueden guardar números, también cadenas de texto, y de varias formas
distintas.

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

Iteración #7: Hacer preguntas al usuario
----------------------------------------

Vamos a obtener datos del usuario::

.. code-block:: python

    print("¿Cómo te llamas?")
    name = input()
    answer = input("¿Cuál es el sentido de la vida, el universo y todo lo demás?")

Iteración #8: Listas, tuplas y diccionarios
-------------------------------------------

Las listas, tuplas y diccionarios son las estructuras de datos
más útiles y usadas en Python.

**Listas**

Similares a los vectores y arrays en otros lenguaes, son mutables y
pueden contener elementos de cualquier tipo.

.. code-block:: python

    >>> some_list = []
    >>> some_list = list()
    >>> list_1 = [1, 2, 3]
    >>> list_2 = ["a", "b", "c"]
    >>> list_3 = ["a", 1, "b", 2]
    >>> nested = [list_1, list_2, list_3]

A los elementos de una lista se puden acceder usando las ``[]``, además, se
pueden trocear usando los ``:``:

.. code-block:: python

    >>> list_1[1]
    2
    >>> list_2[-1]
    "c"
    >>> list_2[:2]
    ["a", "b"]
    >>> list_2[1:]
    ["b", "c"]
    >>> list_2[1:2]
    ["b"]

**Tuplas**

Similar a las listas, pero son inmutables.

.. code-block:: python

    >>> some_tuple = (1, 2, 3)
    >>> some_tuple = tuple()
    >>> some_tuple = tuple([1, 2, 3])

Se puede acceder a los elementos de una tupla de la misma
forma que la lista.

**Diccionarios**

Los diccionarios son *tablas hash*, que están indexados por
cualquier tipo inmutable, como cadenas de texto o números.

.. code-block:: python

    >>> some_dict = {}
    >>> some_dict = dict()
    >>> other_dict = {"one": 1, "two": 2,  "three": 3}

.. code-block:: python

    >>> "one" in other_dict
    True
    >>> other_dict["two"]
    2
    >>> other_dict["five"]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'five'
    >>> "five" in other_dict
    False
