# Arreglos

> var arreglo = [1,2,3]

> var usuario = { nombre: "test", valores : arreglo}

> db.usuarios.insert(usuario)

WriteResult({ "nInserted" : 1 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3 ] }


> db.usuarios.update({}, {$set : { nuevo_arreglo: [ ] } }
... )

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })


> db.usuarios.update({}, {$addToSet: { valores: 4 } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$addToSet: { valores: 4 } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 0 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4 ], "nuevo_arreglo" : [ ] }


> db.usuarios.update({}, {$push: { valores: 4 } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$push: { valores: {$each: [5,6 ] } } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$addToSet: { valores: {$each: [6,7 ] } } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$addToSet: { valores: {$each: [100,101], $position:4 } } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })


> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 100, 101 ], "nuevo_arreglo" : [ ] }


> db.usuarios.update({}, {$push: { valores: {$each: [100,101], $position:4 } } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 100, 101, 4, 5, 6, 7, 100, 101 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$push: { valores: {$each: [95,97], $sort:1 } } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 95, 97, 100, 100, 101, 101 ], "nuevo_arreglo" : [ ] }

> db.usuarios.update({}, {$push: { valores: {$each: [65,72]} } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 95, 97, 100, 100, 101, 101, 65, 72 ], "nuevo_arreglo" : [ ] }


> db.usuarios.update({}, {$push: { valores: {$each: [], $sort:1} } })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 4, 4, 5, 6, 7, 65, 72, 95, 97, 100, 100, 101, 101 ], "nuevo_arreglo" : [ ] }

