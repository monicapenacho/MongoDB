Comentarios borramos el primero que encuentre con el título "Avatar"

Función
db.Movies.findOneAndDelete({title: "Avatar"});

Verificación
db.Movies.find()
