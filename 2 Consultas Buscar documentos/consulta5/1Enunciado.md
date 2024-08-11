5. Obtener todas las películas de los 90s.

Teoría

> = añox y <= año1 Comnentario incluimos los intervalos en la selección y por eso añadimos "e"
> db.NombreDeLaColeccion.find({year:{$gte:añox, $lte:año1}})
