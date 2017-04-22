# Beetwenn

Operadores

$gt >
$gte >=
$lt <
$lte <=



> db.libros.save(libro)

WriteResult({ "nInserted" : 1 })

> db.libros.find()

{ "_id" : ObjectId("58d53e196d23c3f65e31e582"), "nombre" : "El señor de los anillo", "autor" : "Tolkien" }
{ "_id" : ObjectId("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }

> db.libros.remove({_id : ObjectId("58d53e196d23c3f65e31e582")})

WriteResult({ "nRemoved" : 1 })

> db.libros.find()

{ "_id" : ObjectId("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }

> libro = { nombre: "El nombre de la rosa", autor: "Carlos", vendidos: 55}

{ "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }

> db.libros.insert(libro)

WriteResult({ "nInserted" : 1 })

> libro = { nombre: "Star wars", autor: "Carlos", vendidos: 255}

{ "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }

> db.libros.insert(libro)

WriteResult({ "nInserted" : 1 })

> db.libros.find({vendiddos: {$lt : 100}})

> db.libros.find({vendidos: {$lt : 100}})

{ "_id" : ObjectId("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }
{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }

> db.libros.find({vendidos: {$gt : 100}})

{ "_id" : ObjectId("58d53fd66d23c3f65e31e585"), "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }

> db.libros.find({vendidos: {$lt : 100, $gt: 50}})

{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }

> db.libros.find()

{ "_id" : ObjectId("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }
{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }
{ "_id" : ObjectId("58d53fd66d23c3f65e31e585"), "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }

> libro = { nombre: "Star wars", autor: "Carlos", vendidos: 300}

{ "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 300 }


> db.libros.find({vendidos: {$lt : 100, $gt: 50}})

{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }


> db.libros.find({vendidos: {$lt : 100, $gt: 50}}, {autor:1})
{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "autor" : "Carlos" }

