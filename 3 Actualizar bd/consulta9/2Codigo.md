db.Movies.updateOne(
{ title: "Pulp Fiction" },
{ $addToSet: { actors: "Samuel L. Jackson" } }
);

Verificar
db.Movies.findOne({ title: "Pulp Fiction" });
