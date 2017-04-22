# Update 2

> db.usuarios.find()

{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Cambio de nombre" }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }
{ "_id" : ObjectId("58d51e4709655d6e9af14b27"), "nombre" : "Esto es una prueba de save" }

> test = db.usuarios.findOne( {_id : ObjectId("58d51d5209655d6e9af14b25")} )

{
	"_id" : ObjectId("58d51d5209655d6e9af14b25"),
	"nombre" : "Cambio de nombre"
}

> test

{
	"_id" : ObjectId("58d51d5209655d6e9af14b25"),
	"nombre" : "Cambio de nombre"
}

> test.nombre

Cambio de nombre

> test.nombre = "Podemos Actualizar el nombre"

Podemos Actualizar el nombre

> test.nombre

Podemos Actualizar el nombre

> test.edad

> test.edad = 22

22

> test

{
	"_id" : ObjectId("58d51d5209655d6e9af14b25"),
	"nombre" : "Podemos Actualizar el nombre",
	"edad" : 22
}

> db.usuarios.update( { _id: ObjectId("58d51d5209655d6e9af14b25")}, test )
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Podemos Actualizar el nombre", "edad" : 22 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }
{ "_id" : ObjectId("58d51e4709655d6e9af14b27"), "nombre" : "Esto es una prueba de save" }


> db.usuarios.findOne()

{
	"_id" : ObjectId("58d5135109655d6e9af14b1e"),
	"nombre" : "Test",
	"edad" : 23
}

