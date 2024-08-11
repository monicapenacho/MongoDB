Obtener las películas estrenadas entre el año 2000 y 2010.

Comentario EXCLUIR LOS INTERVALOS para usar una función diferente a la consulta 5

Teoría
Hipótesis el año x y año 1 no queremos incluirlo en la selección
db.NombreDeLaColeccion.find({year:{$gt:añox, $lt:año1}})
