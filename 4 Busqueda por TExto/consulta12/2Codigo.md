Opción 1 búsqueda con expresión regular regex

db.Movies.find({
synopsis: {
$regex: "Bilbo",
$not: { $regex: "Gandalf" }
}
});

Opción 2 búsqueda con indices

2.1 Verificar que tengo el índice de texto para synopsis

db.Movies.getIndexes();
como es synopsis nos vale el índice anterior

2.2 Búsqueda
db.Movies.find({
$text: {
$search: "Bilbo -Gandalf"
}
});
