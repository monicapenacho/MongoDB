<!-- Opción 1 Indice de texto -->

1.1 Confirmar que existe el indice text para synospsis

db.Movies.getIndexes()

1.2 Buscar

db.Movies.find({
$text: {
$search: "\"gold\"\"dragon\""
}

});

<!-- Opción 2 Regex -->

db.Movies.find({
$and: [
{ synopsis: { $regex: "gold", $options: "i" } },
{ synopsis: { $regex: "dragon", $options: "i" } }
]
});
