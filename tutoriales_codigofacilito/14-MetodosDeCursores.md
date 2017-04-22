# Arreglos (Eliminar elementos)

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 65, 72, 95, 97, 100, 100, 101, 101 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$pull: { valores: 65} })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 72, 95, 97, 100, 100, 101, 101 ], "nuevo_arreglo" : [ ] }
 
> db.usuarios.update({}, {$pull: { valores: {$gte : 50}} })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7 ], "nuevo_arreglo" : [ ] }


> db.usuarios.update({}, {$pullAll: { valores: [4,5] } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 6, 7 ], "nuevo_arreglo" : [ ] }
