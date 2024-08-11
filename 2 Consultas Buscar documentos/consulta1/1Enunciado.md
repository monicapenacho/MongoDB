1. Obtener todos los documentos

Teoría
paso 1 insertar documentos
db.nombre_de_la_coleccion.insertOne({ campo1: "valor1", campo2: "valor2" })
db.nombre_de_la_coleccion.insertMany([{ campo1: "valor1", campo2: "valor2" }, {}, {}])
En caso de error para borrar
db.nombreDeTuColeccion.deleteOne({ \_id: ObjectId("id_del_documento") })
paso 2 obtener todos los documentos
db.nombre_de_la_coleccion.find()
