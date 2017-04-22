# Delete

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

> db.usuarios.remove( { nombre: "CF" })

WriteResult({ "nRemoved" : 0 })

> db.usuarios.remove( { nombre: "CF2" })

WriteResult({ "nRemoved" : 3 })

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

> db.usuarios.update({}, {$set:{nombre: "iguales"}} , {multi:true})

WriteResult({ "nMatched" : 9, "nUpserted" : 0, "nModified" : 9 })

> db.usuarios.find()

{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "iguales", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "iguales", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "iguales" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro", "nombre" : "iguales" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "iguales", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "iguales", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "iguales", "edad" : 22 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "iguales" }
{ "_id" : ObjectId("58d51e4709655d6e9af14b27"), "nombre" : "iguales" }

> db.usuarios.remove(nombre: "iguales")

2017-03-24T14:47:05.089+0100 E QUERY    [thread1] SyntaxError: missing ) after argument list @(shell):1:25

> db.usuarios.remove(nombre: "iguales")

2017-03-24T14:47:11.648+0100 E QUERY    [thread1] SyntaxError: missing ) after argument list @(shell):1:25

> db.usuarios.remove({nombre: "iguales"})

WriteResult({ "nRemoved" : 9 })

> db.usuarios.find()

> uno = { nombre : "Uno" }

{ "nombre" : "Uno" }

> db.usuarios.insert(uno)

WriteResult({ "nInserted" : 1 })

> db.usuarios.remove({})

WriteResult({ "nRemoved" : 1 })

> db.usuarios.find()

> db.usuarios.drop()

true

> show collections

usuarios2

> db.usuarios2.drop()

true

> show collections

> db

codigofacilito

> db.dropDatabase()

{ "dropped" : "codigofacilito", "ok" : 1 }

> db

codigofacilito

> show dbs

admin  0.000GB
local  0.000GB
test   0.000GB



