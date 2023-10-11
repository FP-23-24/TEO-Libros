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

1. Función ``lee_libros``, que dado el nombre de un archivo csv, devuelve una lista de tipo Libro con todos los libros leídos del fichero. **NOTA**: Para convertir una cadena a fecha use lo siguiente:```fecha_publicacion = datetime.strptime(fecha_publicacion, "%d/%m/%Y").date()```. Cree una función auxiliar a_booleno para convertir la cadena si y la cadena no, a verdadero y falso, respectivamente.
1. Función ``numero_autores_distintos``, que recibe una lista de libros, y devuelve el número de autores distintos de los que hay libros en la biblioteca.
1. Función ``libros_de_autor``, que recibe una lista de libros y una cadena ``autor``, con el nombre de un autor y devuelve una lista con todos los libros del autor disponible en la biblioteca.
1. Función ``titulos_libros_de_anyo``, que recibe una lista de libros y una un entero anyo, y devuelve una lista con  los títulos de los libros que se publicaron ese año.
1. Función ``autores_disponibles``, que recibe una lista de libros y una cadena ``inicial`` y devuelve una lista ordenada alfabéticamente con los nombres de los autores cuya inicial es la indicada y para los que hay libros en stock en la librería. La lista no puede contener duplicados.
1. Función ``titulos_baratos_actuales``, que recibe una lista de libros y devuelve una lista con los títulos de los libros con un precio a 20 euros que hayan sido publicados a partir del año 2001.
1. Función ``media_precios``, que recibe una lista de libros y una cadena de texto ``palabra`` y devuelve la media del precio de los libros que contienen en su título la ``palabra`` en cuestión. Si no se encuentra ningún libro con dicha palabra en el título, la función devuelve ``None``. **NOTA**: La búsqueda de los libros con la palabra en el título no debe ser sensible a mayúsculas.
1. Función ``libro_mas_reciente``, que recibe una lista de libros y devuelve el libro con la fecha de publicación más reciente.

Al probar las funciones, debe obtener una salida parecida a esta:

```
test_lee_fichero ================================================================================================
Se han leido 31 libros
Los tres primeros son:
[Libro(isbn='978-3-16-511131-0', titulo='El Gran Gatsby', autor='F. Scott Fitzgerald', fecha_publicacion=datetime.date(1925, 4, 10), precio=10.85, disponible=False), Libro(isbn='978-3-16-444141-0', titulo='1984', autor='George Orwell', fecha_publicacion=datetime.date(1949, 6, 8), precio=26.69, disponible=True), Libro(isbn='978-3-16-691370-0', titulo='Un mundo feliz', autor='Aldous Huxley', fecha_publicacion=datetime.date(1932, 9, 1), precio=35.59, disponible=True)]
Los tres últimos son:
[Libro(isbn='978-8-49-989373-0', titulo='Un mundo sin fin', autor='Ken Follett', fecha_publicacion=datetime.date(2012, 1, 12), precio=15.97, disponible=False), Libro(isbn='978-8-46-635105-8', titulo='Una columna de fuego', autor='Ken Follett', fecha_publicacion=datetime.date(2020, 7, 16), precio=15.97, disponible=False), Libro(isbn='978-3-16-982362-0', titulo='El código Da Vinci', autor='Dan Brown', fecha_publicacion=datetime.date(2003, 3, 18), precio=29.81, disponible=False)]

test_numero_autores_distintos ================================================================================================
En la biblioteca hay 28 autores distintos

test_libros_de_autor ================================================================================================
Los libros de Ken Follett en la biblioteca son:
Libro(isbn='978-3-16-534649-0', titulo='Los pilares de la tierra', autor='Ken Follett', fecha_publicacion=datetime.date(1989, 9, 1), precio=15.97, disponible=False)    
Libro(isbn='978-8-49-989373-0', titulo='Un mundo sin fin', autor='Ken Follett', fecha_publicacion=datetime.date(2012, 1, 12), precio=15.97, disponible=False)
Libro(isbn='978-8-46-635105-8', titulo='Una columna de fuego', autor='Ken Follett', fecha_publicacion=datetime.date(2020, 7, 16), precio=15.97, disponible=False) 

test_libros_de_anyo ================================================================================================
Los títulos de los libros publicados en el año 2020 son:
Una columna de fuego

test_autores_disponibles ================================================================================================
Autores disponibles que comienzan por 'M': ['Margaret Atwood', 'Margaret Mitchell', 'Mark Twain', 'Miguel de Cervantes']

test_titulos_baratos_actuales ================================================================================================
Titulos baratos actuales: ['La carretera', 'La sombra del viento', 'La chica con el tatuaje de dragón', 'La chica del tren']

test_media_precios ================================================================================================
Media de precios de libros con la palabra 'El': 25.093571428571426

test_libro_mas_reciente ================================================================================================
Libro más reciente: Libro(isbn='978-3-16-392611-0', titulo='La chica del tren', autor='Paula Hawkins', fecha_publicacion=datetime.date(2015, 1, 13), precio=8.34, disponible=False)
```
