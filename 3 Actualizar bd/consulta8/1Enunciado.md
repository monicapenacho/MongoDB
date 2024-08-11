8. Agregar sinopsis a "The Hobbit: The Desolation of Smaug" : "The dwarves, along with
   Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their
   homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical
   ring."

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
