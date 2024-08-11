<!--
Opción 1 Búsqueda por Indice text -->

1.1. Verificar que existe el indice para SYNOSPSIS

db.Movies.getIndexes();

Como existe no hay que crearlo

1.2
db.Movies.find ({
$text: {
$search: "dwarves hobbit"
}
});

<!--
Opción 2 Búsqueda por Expresión REgular Regex -->

db.Movies.find({
$or: [
{ synopsis: { $regex: "dwarves", $options: "i" } },
{ synopsis: { $regex: "hobbit", $options: "i" } }
]
});
