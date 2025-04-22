Este programa es una funcion en AWS Lambda que permite 
almacenar informacion sobre prestamos de libros en la 
tabala en dynamodb PRestamosLibros. LA funcion recibe los datos 
del test en formato Json y de ahi se conecta a la BD y se
ingresan 
Se utiliza el cliente de DynamoDB de AWS para insertar
los datos en la tabla PrestamosLibros.
La respuesta indica si la operación fue exitosa
Código HTTP 200: Inserción exitosa.
Código HTTP 500: Error.
