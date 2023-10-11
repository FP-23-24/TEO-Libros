# TEO-Libros

Tenemos un fichero CSV con registros de libros en una librería (se muestra la primera línea del fichero):

```
978-3-16-148410-0, El Gran Gatsby, F. Scott Fitzgerald, 10/04/1925, 12.99, True
```

Las columnas son:

* ISBN (str): Identificador único de cada libro.
* Título (str): Título del libro.
* Autor (str): Nombre del autor del libro.
* Fecha de publicación (date): Fecha en la que fue publicado el libro.
* Precio (float): Precio de venta en euros.
* Disponible (bool): Indica si el libro está en stock.

Se dispone de la siguiente namedtuple  para representar esta información:

```
Libro = namedtuple("Libro", "isbn,titulo,autor,fecha_publicacion,precio,disponible")
```

Implemente las siguientes funciones:

* Función ``lee_libros``, que dado el nombre de un archivo csv, devuelve una lista de tipo Libro con todos los libros leídos del fichero.
* Función ``numero_autores_distintos``, que recibe una lista de libros, y devuelve el número de autores distintos de los que hay libros en la biblioteca.
* Función ``libros_autor``, que recibe una lista de libros y una cadena ``autor``, con el nombre de un autor y devuelve una lista con todos los libros del autor disponible en la biblioteca.
* Función ``autores_disponibles``, que recibe una lista de libros y una cadena ``inicial`` y devuelve una lista ordenada alfabéticamente con los nombres de los autores cuya inicial es la indicada y para los que hay libros en stock en la librería. La lista no puede contener duplicados.
* Función ``titulos_baratos_actuales``, que recibe una lista de libros y devuelve una lista con los títulos de los libros con un precio a 20 euros que hayan sido publicados a partir del año 2001.
* Función ``media_precios``, que recibe una lista de libros y una cadena de texto ``palabra`` y devuelve la media del precio de los libros que contienen en su título la ``palabra`` en cuestión. Si no se encuentra ningún libro con dicha palabra en el título, la función devuelve ``None``. **NOTA**: La búsqueda de los libros con la palabra en el título no debe ser sensible a mayúsculas.
* Función ``libro_mas_reciente``, que recibe una lista de libros y devuelve el libro con la fecha de publicación más reciente.

Al probar las funciones, debe obtener una salida parecida a esta:

```
Autores disponibles que comienzan por 'M': ['Margaret Atwood', 'Margaret Mitchell', 'Mark Twain', 'Miguel de Cervantes']
Titulos baratos actuales: ['La carretera', 'La sombra del viento', 'La chica con el tatuaje de dragón', 'La chica del tren']
Media de precios de libros con la palabra 'El': 25.093571428571426
Libro más reciente: Libro(isbn='978-3-16-392611-0', titulo='La chica del tren', autor='Paula Hawkins', fecha_publicacion=datetime.date(2015, 1, 13), precio=8.34, disponible=False)
```
