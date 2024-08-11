14. Encontrar las películas que en la sinopsis contengan la palabra "gold" y "dragon"

Teoría

<!-- Opción 1 indice de texto -->

1. Sin Comillas Dobles: "OR" Implícito
   Cuando usas $search sin comillas dobles alrededor de las palabras, MongoDB trata las palabras como conectadas por un "OR" implícito. Esto significa que buscará documentos que contengan cualquiera de las palabras en el campo indexado.

Ejemplo:
javascript
Copiar código
db.Movies.find({
$text: {
$search: "dwarves hobbit"
}
});
Significado: Esta búsqueda devolverá documentos que contengan "dwarves", "hobbit", o ambas palabras en el campo synopsis.
Resultado: Se comporta como un "OR" implícito: los documentos que contienen al menos una de las palabras serán devueltos.

<!-- 2. Con Comillas Dobles: "AND" Implícito (Frases Exactas) -->

Cuando usas comillas dobles alrededor de las palabras o frases, MongoDB trata cada conjunto entre comillas como un todo, y todos deben estar presentes para que el documento coincida. Esto se comporta como un "AND" implícito.

Ejemplo:
javascript
Copiar código
db.Movies.find({
$text: {
$search: "\"dwarves\" \"hobbit\""
}
});
Significado: Esta búsqueda devolverá documentos que contengan ambas palabras "dwarves" y "hobbit" en cualquier orden o lugar dentro del campo synopsis.
Resultado: Se comporta como un "AND" implícito: solo los documentos que contienen ambas palabras serán devueltos.

Recapitulación:
Sin Comillas Dobles: "dwarves hobbit" actúa como un "OR". Devuelve documentos que contienen al menos una de las palabras.
Con Comillas Dobles: \"dwarves\" \"hobbit\" actúa como un "AND". Devuelve documentos que contienen todas las palabras/frases.

<!-- Opción 2 Regex -->

Uso de $and
Si deseas encontrar documentos que cumplan varias condiciones al mismo tiempo, puedes usar el operador $and.
