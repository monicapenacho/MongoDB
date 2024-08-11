10. Encontrar las películas que en el título contengan la palabra "Hobbit"

Teoría

<!-- Opción 1 Búsqueda con Expresión Regular (regex) -->

Rendimiento
Rendimiento: Usar expresiones regulares puede ser menos eficiente, especialmente si estás buscando en una colección grande. Esto se debe a que MongoDB tendrá que escanear cada documento en la colección para encontrar coincidencias, a diferencia de los índices de texto que pueden optimizar la búsqueda.

Flexibilidad: Las expresiones regulares ofrecen mucha flexibilidad en la búsqueda, permitiendo patrones complejos, pero a costa de eficiencia.

Explicación:
$regex: "Hobbit": Busca títulos que contengan la palabra "Hobbit".
$options: "i": Hace que la búsqueda sea insensible a mayúsculas y minúsculas (i de "ignore case").

Expresión completa
db.Movies.find({ title: { $regex: "Hobbit", $options: "i" } });

Expresión simplificada
db.Movies.find({ title: /Hobbit/i });

Explicación del uso de regex
title: /Hobbit/i: Busca películas cuyo título contiene la palabra "Hobbit". El i al final de la expresión regular hace que la búsqueda sea insensible a mayúsculas y minúsculas.

<!-- Opción 2 Búsqueda con índice de texto -->

2.1 Crear indice de texto
db.Movies.createIndex({ title: "text" });
2.2 Buscar por texto
db.Movies.find({ $text: { $search: "Hobbit" } });
