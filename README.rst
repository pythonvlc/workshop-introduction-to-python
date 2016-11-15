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

Iteración #9: Condiciones
-------------------------

.. code-block:: python

    cats = input("¿Cuantos gatos tienes?")
    if cats < 2:
        print("Igual está muy solo")
    elif cats == 2:
        print("¡Es el número perfecto!")
    elif 2 < cats <= 5:
        print("¿Seguro que puedes cuidarlos a todos bien?")
    else:
        print("No te diré yo que son demasiados... pero...")

**Operadores booleanos**

* ``or``
* ``and``
* ``not``

La evaluación de ``[]``, ``()``, ``""`` y ``None`` siempre resulta en ``False``.

Iteración #10: Bucles
---------------------

**Bucle for**

.. code-block:: python

    >>> for number in range(5):
            print(number)
    0
    1
    2
    3
    4
    5
    >>> a_dict = {"one":1, "two":2, "three":3}
    >>> for key in a_dict:
            print(key)
    "three"
    "two"
    "one"

**Bucle while**

.. code-block:: python

    >>> i = 0
    >>> while i < 10:
            print(i)
            i += 1
    0
    1
    2
    3
    4
    5
    6
    7
    8
    9

Iteración #11: Compresiones
---------------------------

**Copresión de listas**

.. code-block:: python

    >>> x = ['1', '2', '3', '4', '5']
    >>> y = [int(i) for i in x]
    >>> y
    [1, 2, 3, 4, 5]
    >>> vec = [[1,2,3], [4,5,6], [7,8,9]]
    >>> [num for elem in vec for num in elem]
    [1, 2, 3, 4, 5, 6, 7, 8, 9]

**Copresión de diccionarios**

.. code-block:: python

    >>> d = {i: str(i) for i in range(5)}
    >>> print(d)
    {0: '0', 1: '1', 2: '2', 3: '3', 4: '4'}

Iteración #12: Manejando excepciones
------------------------------------

.. code-block:: python

    other_dict = {"one": 1, "two": 2,  "three": 3}
    key = "five"
    try:
        other_dict[key]
    except KeyError:
        print("La calve %s no existe en el diccionario" % key)
    else:
        print("La calve %s se ha encontrado en el diccionario" % key)
    finally:
        print("¡Y seguimos ejecutando!")

**Excepciones comunes**

* Exception
* AttributeError
* IOError
* ImportError
* IndexError
* KeyError
* KeyboardInterrupt
* NameError
* OSError
* SyntaxError
* TypeError
* ValueError
* ZeroDivisionError


Iteración #13: Trabajando con ficheros
--------------------------------------

.. code-block:: python

    with open("test.txt") as file_handler:
        for line in file_handler:
            print(line)

Iteración #14: Módulos y paquetes
---------------------------------

* Cada fichero ``.py`` es un **módulo**
* Una carpeta con un fichero llamado ``__init__.py`` es un paquete

.. code-block:: python

    >>> import this
    The Zen of Python, by Tim Peters

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!

.. code-block:: python

    >>> import math
    >>> math.sqrt(4)
    2.0

.. code-block:: python

    >>> from math import sqrt
    >>> sqrt(16)
    4.0

Iteración #15: Funciones
------------------------


Iteración #16: Clases
---------------------
