16. Eliminar la película "Avatar"

Comentarios borramos el primero que encuentre con el título "Avatar"

Teoría

db.Colección.findOneAndDelete({ XXX: "YYY" });

db.Movies.findOneAndDelete(...): Este método busca el primer documento que coincida con el filtro proporcionado y lo elimina de la colección. En este caso, estás buscando un documento cuyo campo XXX sea "YYY".
