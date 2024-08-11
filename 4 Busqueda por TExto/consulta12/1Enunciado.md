12. Encontrar las películas que en la sinopsis contengan la palabra "Bilbo" y no la palabra
    "Gandalf"

Teoría

<!-- Opción 1 búsqueda con expresión regular regex -->

db.Movies.find({
synopsis: {
$regex: "Bilbo",
$not: { $regex: "Gandalf" }
}
});

$regex: "Bilbo": Busca todas las sinopsis que contengan la palabra "Bilbo".
$not: { $regex: "Gandalf" }: Excluye las sinopsis que contengan la palabra "Gandalf".

<!-- Opción 2 búsqueda con índice de texto -->

Asegúrate de tener un índice de texto en synopsis:

db.Movies.createIndex({ synopsis: "text" });
Realiza la búsqueda:

db.Movies.find({
$text: {
$search: "Bilbo -Gandalf"
}
});
"Bilbo -Gandalf": La cadena de búsqueda incluye "Bilbo" y excluye "Gandalf". El signo menos - antes de "Gandalf" indica que deseas excluir los documentos que contengan esta palabra en el campo indexado (synopsis).
