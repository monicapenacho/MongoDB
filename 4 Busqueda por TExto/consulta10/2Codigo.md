comentarios
Opción 1 Búsqueda con Expresión Regular (regex)
Búsqueda independientemente de si está en mayúsculas o minúsculas

db.Movies.find({ title: { $regex: "Hobbit", $options: "i" } });

Opción 2 Búsqueda con indice de texto

2.1 Crear indice de texto
db.Movies.createIndex({ title: "text" });
2.2 Buscar por texto
db.Movies.find({ $text: { $search: "Hobbit" } });
