9. Agregar una actor llamado "Samuel L. Jackson" a la película "Pulp Fiction"

Teoría
La diferencia principal entre los operadores $push y $addToSet en MongoDB radica en cómo manejan la adición de elementos a un array:

<!--
1. Operador $push -->

Descripción: El operador $push agrega un elemento al final de un array, independientemente de si el elemento ya existe en el array.
Uso: Se utiliza cuando deseas agregar un elemento a un array sin preocuparte por la duplicación de elementos.
Ejemplo:
javascript
Copiar código
db.Movies.updateOne(
{ title: "Pulp Fiction" },
{ $push: { actors: "Samuel L. Jackson" } }
);
Resultado: Si "Samuel L. Jackson" ya está en la lista de actors, este operador lo agregará nuevamente, creando duplicados.

<!--
2. Operador $addToSet -->

    Descripción: El operador $addToSet agrega un elemento a un array solo si el elemento no existe ya en el array. En otras palabras, previene la duplicación de elementos dentro del array.
    Uso: Se utiliza cuando deseas agregar un elemento a un array pero solo si aún no está presente.
    Ejemplo:
    javascript
    Copiar código
    db.Movies.updateOne(
    { title: "Pulp Fiction" },
    { $addToSet: { actors: "Samuel L. Jackson" } }
    );
    Resultado: Si "Samuel L. Jackson" ya está en la lista de actors, este operador no agregará el nombre nuevamente, evitando duplicados.

<!-- Resumen de Diferencias -->

$push: Siempre agrega el elemento al array, lo que puede resultar en duplicados.
$addToSet: Solo agrega el elemento si no está presente en el array, evitando duplicados.
