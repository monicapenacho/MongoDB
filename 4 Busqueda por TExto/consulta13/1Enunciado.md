13. Encontrar las películas que en la sinopsis contengan la palabra "dwarves" ó "hobbit"

Teoría

<!-- Opción 1: Usando un Índice de Texto -->

Crear un índice de texto en el campo synopsis (si no lo has hecho ya):

db.Movies.createIndex({ synopsis: "text" });
Realizar la búsqueda con $text:

db.Movies.find({
$text: { 
    $search: "dwarves hobbit" 
  } 
});
$search: "dwarves hobbit": Busca documentos que contengan cualquiera de las palabras "dwarves" o "hobbit" en el campo synopsis.

% Opción 2: Usando Expresiones Regulares (regex)

db.Movies.find({
$or: [
    { synopsis: { $regex: "dwarves", $options: "i" } },
    { synopsis: { $regex: "hobbit", $options: "i" } }
  ]
});
$or: Utiliza $or para buscar documentos donde al menos una de las condiciones sea verdadera.
$regex: "dwarves", $options: "i": Busca la palabra "dwarves" en el campo synopsis de manera insensible a mayúsculas/minúsculas.
$regex: "hobbit", $options: "i": Similar al anterior, busca la palabra "hobbit".

<!-- Resumen de los Métodos: -->

Con Índice de Texto: Es más eficiente en términos de rendimiento, especialmente en grandes colecciones, y permite realizar búsquedas más rápidas y precisas.
Con Expresiones Regulares: Proporciona flexibilidad y no requiere la creación de un índice, pero puede ser más lento, especialmente en colecciones grandes.
Ambos métodos te permitirán encontrar las películas cuya sinopsis contenga "dwarves" o "hobbit", y puedes elegir el que mejor se ajuste a tu situación.
