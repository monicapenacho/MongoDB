15. Eliminar la película "Pee Wee Herman's Big Adventure"

Teoría: funciona similar a la función de insert

Comando para borrar la película:
javascript
Copiar código
db.Movies.deleteOne({ \_id: ObjectId("66b864a4add9612b18228fbb") });
Explicación del Comando:
db.Movies.deleteOne: Este método elimina un solo documento que coincida con el filtro proporcionado.
{ \_id: ObjectId("66b864a4add9612b18228fbb") }: Este es el filtro que busca el documento con el \_id específico 66b864a4add9612b18228fbb.
Confirmación de la Eliminación:
Después de ejecutar este comando, si quieres verificar que la película ha sido eliminada, puedes intentar buscarla nuevamente:

Explicación del Código:
db.Movies.deleteOne(...): Este método elimina un solo documento que coincida con el filtro proporcionado. En este caso, estamos buscando un documento cuyo \_id sea 66b864a4add9612b18228fbb.
{ \_id: ObjectId('66b864a4add9612b18228fbb') }: Este es el filtro que identifica el documento a eliminar por su \_id. Se utiliza ObjectId para asegurarse de que el \_id se interprete correctamente como un objeto BSON en MongoDB.
