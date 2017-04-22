# Cursores 2


Ascendente 1

descendente -1


> db.libros.find().count()

3

> db.libros.find().sort({autor:1})

{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }
{ "_id" : ObjectId("58d53fd66d23c3f65e31e585"), "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }
{ "_id" : ObjectId("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }

> db.libros.find().sort({autor:1}).limit(2)

{ "_id" : ObjectId("58d53fc76d23c3f65e31e584"), "nombre" : "El nombre de la rosa", "autor" : "Carlos", "vendidos" : 55 }
{ "_id" : ObjectId("58d53fd66d23c3f65e31e585"), "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }

//se puede obtener el segundo libro más vendido

> db.libros.find().sort({autor:1}).skip(1).limit(2)

{ "_id" : ObjectId("58d53fd66d23c3f65e31e585"), "nombre" : "Star wars", "autor" : "Carlos", "vendidos" : 255 }
{ "_id" : ObjectId.("58d53f7b6d23c3f65e31e583"), "nombre" : "El señor de los anillo", "autor" : "Tolkien", "vendidos" : 15 }


> db.libros.find().sort({autor:1}).skip(1).size()

2

