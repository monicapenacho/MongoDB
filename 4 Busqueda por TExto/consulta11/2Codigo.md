comentarios
Opción 1 Búsqueda con Expresión Regular (regex)
Búsqueda independientemente de si está en mayúsculas o minúsculas

db.Movies.find({ synopsis: { $regex: "Gandalf", $options: "i"}});

Opción 2 Búsqueda con indice de texto

2.1 Crear indice de texto
2.1.1 consultar si existe indice
db.Movies.getIndexes();

<!-- [
  { v: 2, key: { _id: 1 }, name: '_id_' },
  {
    v: 2,
    key: { _fts: 'text', _ftsx: 1 },
    name: 'title_text',
    weights: { title: 1 },
    default_language: 'english',
    language_override: 'language',
    textIndexVersion: 3
  }
] -->

2.1.2 si existe indice borrarlo
db.Movies.dropIndex("title_text");

2.1.3. Verificar borrado
db.Movies.getIndexes();

2.1.4 crear nuevo indice
db.Movies.createIndex({ synopsis: "text" });

2.2 Buscar por texto
db.Movies.find({ $text: { $search: "Gandalf" }});
