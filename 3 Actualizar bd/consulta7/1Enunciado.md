7. Agregar sinopsis a "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo
   Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim
   their mountain home - and the gold within it - from the dragon Smaug."

   Teoría
   Comentario: con id

db.Collection.updateOne(
{ \_id:ObjectId('') },
{ $set:{campo:"texto"} }
);

db.Movies.updateOne(
{ \_id:ObjectId('')},
{ $set:{synopsis:""} }
);
