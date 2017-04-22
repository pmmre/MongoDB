# Update 3

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

> crear_prueba = { nombre : "Carlos", edad : 25 }
{ "nombre" : "Carlos", "edad" : 25 }

> db.usuarios.insert([crear_prueba, crear_prueba, crear_prueba ])

BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 3,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "Carlos", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "Carlos", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "Carlos", "edad" : 25 }

> db.usuarios.update({nombre:"Carlos"}, {$set : {nombre: "CF" }})

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "Carlos", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "Carlos", "edad" : 25 }

> db.usuarios.update({nombre:"Carlos"}, {$set : {nombre: "CF" }}, {multi: true})

WriteResult({ "nMatched" : 2, "nUpserted" : 0, "nModified" : 2 })

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF", "edad" : 25 }

> db.usuarios.update({nombre:"Carlos"}, {$set : {edad: "27" }}, {multi: true})

WriteResult({ "nMatched" : 0, "nUpserted" : 0, "nModified" : 0 })

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF", "edad" : 25 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF", "edad" : 25 }

> db.usuarios.update({nombre:"CF"}, {$set : {edad: "27" }}, {multi: true})

WriteResult({ "nMatched" : 3, "nUpserted" : 0, "nModified" : 3 })

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF", "edad" : "27" }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF", "edad" : "27" }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF", "edad" : "27" }

> db.usuarios.update({nombre:"CF"}, {$set : {edad: "27", nombre: "CF2", example:56 }}, {multi: true})

WriteResult({ "nMatched" : 3, "nUpserted" : 0, "nModified" : 3 })

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF2", "edad" : "27", "example" : 56 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF2", "edad" : "27", "example" : 56 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF2", "edad" : "27", "example" : 56 }

> db.usuarios.update({}, {$set : {example:86 }}, {multi: true})

WriteResult({ "nMatched" : 12, "nUpserted" : 0, "nModified" : 12 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23, "example" : 86 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23, "example" : 86 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro", "example" : 86 }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro", "example" : 86 }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22, "example" : 86 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23, "example" : 86 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Podemos Actualizar el nombre", "edad" : 22, "example" : 86 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos", "example" : 86 }
{ "_id" : ObjectId("58d51e4709655d6e9af14b27"), "nombre" : "Esto es una prueba de save", "example" : 86 }
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF2", "edad" : "27", "example" : 86 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF2", "edad" : "27", "example" : 86 }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF2", "edad" : "27", "example" : 86 }

> db.usuarios.update({}, {$unset : {example:1 }}, {multi: true})

WriteResult({ "nMatched" : 12, "nUpserted" : 0, "nModified" : 12 })

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
{ "_id" : ObjectId("58d520a865fd821337bc5e79"), "nombre" : "CF2", "edad" : "27" }
{ "_id" : ObjectId("58d520a865fd821337bc5e7a"), "nombre" : "CF2", "edad" : "27" }
{ "_id" : ObjectId("58d520a865fd821337bc5e7b"), "nombre" : "CF2", "edad" : "27" }
 
