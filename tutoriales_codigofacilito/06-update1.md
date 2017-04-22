# Update 1

> uno  = { nombre: "Test uno" }

{ "nombre" : "Test uno" }


> dos = {nombre : "Test dos"}

{ "nombre" : "Test dos" }

> db.usuarios.insert([uno,dos])

BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 2,
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
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Test uno" }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }

> var test = db.usuarios.findOne({ nombre: "Test uno" })


> var test = db.usuarios.findOne({ _id: ObjectId("58d51d5209655d6e9af14b25") })


> test.nombre

Test uno

> test.nombre = "Cambio de nombre"

Cambio de nombre

> test

{
	"_id" : ObjectId("58d51d5209655d6e9af14b25"),
	"nombre" : "Cambio de nombre"
}

> db.usuarios.find()

<code>
{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Test uno" }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }
</code>

> db.usuarios.save(test)

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

```
{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Cambio de nombre" }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }ç
```


> save_prueba = {nombre : "Esto es una prueba de save" }

{ "nombre" : "Esto es una prueba de save" }

> db.usuarios.save(save_prueba)

WriteResult({ "nInserted" : 1 })

> db.usuarios.find()

```
{ "_id" : ObjectId("58d5135109655d6e9af14b1e"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d513f309655d6e9af14b20"), "nombre" : "Test", "edad" : 23 }
{ "_id" : ObjectId("58d51a7109655d6e9af14b21"), "nombre" : "Otro" }
{ "_id" : ObjectId("58d51a8a09655d6e9af14b22"), "la" : "Otro" }
{ "_id" : ObjectId("58d51bad09655d6e9af14b23"), "nombre" : "Eduardo", "edad" : 22 }
{ "_id" : ObjectId("58d51baf09655d6e9af14b24"), "nombre" : "Eduardo", "edad" : 23 }
{ "_id" : ObjectId("58d51d5209655d6e9af14b25"), "nombre" : "Cambio de nombre" }
{ "_id" : ObjectId("58d51d5209655d6e9af14b26"), "nombre" : "Test dos" }
{ "_id" : ObjectId("58d51e4709655d6e9af14b27"), "nombre" : "Esto es una prueba de save" }
```
