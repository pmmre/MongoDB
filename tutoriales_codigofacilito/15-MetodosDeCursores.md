# Arreglos. Selecionar elementos dentro de los arreglos.

> db.usuarios.find()

{ "_id" : ObjectId("58d5499f6d23c3f65e31e5ea"), "nombre" : "test", "valores" : [ 1, 2, 3, 6, 7 ], "nuevo_arreglo" : [ ] }

> db.usuarios.remove({_id :ObjectId("58d5499f6d23c3f65e31e5ea")})

WriteResult({ "nRemoved" : 1 })


> usuario = {nombre = "Eduardo", ejemplo = ["MongoDB", "C#", "SQL", "Java", "Python"] })

2017-03-24T17:51:34.578+0100 E QUERY    [thread1] SyntaxError: missing : after property id @(shell):1:18

> db.usuarios.insert(usuario)

WriteResult({ "nInserted" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d54e9f6d23c3f65e31e5eb"), "nombre" : "test", "valores" : [ 1, 2, 3 ] }

> db.usuarios.remove({_id :ObjectId("58d5499f6d23c3f65e31e5ea")})

WriteResult({ "nRemoved" : 0 })

> db.usuarios.find()

{ "_id" : ObjectId("58d54e9f6d23c3f65e31e5eb"), "nombre" : "test", "valores" : [ 1, 2, 3 ] }

> db.usuarios.remove({_id :ObjectId("58d54e9f6d23c3f65e31e5eb")})

WriteResult({ "nRemoved" : 1 })

> db.usuarios.find()

> usuario

{ "nombre" : "test", "valores" : [ 1, 2, 3 ] }


> var usuario = {nombre : "Eduardo", ejemplo : ["MongoDB", "C#", "SQL", "Java", "Python"] }

> usuario

{
	"nombre" : "Eduardo",
	"ejemplo" : [
		"MongoDB",
		"C#",
		"SQL",
		"Java",
		"Python"
	]
}

> db.usuarios.insert(usuario)

WriteResult({ "nInserted" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d54f166d23c3f65e31e5ec"), "nombre" : "Eduardo", "ejemplo" : [ "MongoDB", "C#", "SQL", "Java", "Python" ] }

> db.usuarios.find( {}, {_id:false, ejemplo:true})

{ "ejemplo" : [ "MongoDB", "C#", "SQL", "Java", "Python" ] }


> db.usuarios.find( {}, {_id:false, ejemplo: {$slice:3} }) 

{ "nombre" : "Eduardo", "ejemplo" : [ "MongoDB", "C#", "SQL" ] }

> db.usuarios.find( {}, {_id:false, ejemplo: {$slice:1} })

{ "nombre" : "Eduardo", "ejemplo" : [ "MongoDB" ] }

> db.usuarios.find( {}, {_id:false, ejemplo: {$slice:-1} })

{ "nombre" : "Eduardo", "ejemplo" : [ "Python" ] }

> db.usuarios.find( {}, {_id:false, ejemplo: {$slice:[ 1,3]  } })

{ "nombre" : "Eduardo", "ejemplo" : [ "C#", "SQL", "Java" ] }

> db.usuarios.find( {}, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "C#", "SQL", "Java" ] }

> db.usuarios.find( { ejemplo: {$in: ["MongoDB"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "C#", "SQL", "Java" ] }

> db.usuarios.find( { ejemplo: {$in: ["XML"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

> db.usuarios.find( { ejemplo: {$in: ["XML","MongoDB"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "C#", "SQL", "Java" ] }

> db.usuarios.find( { ejemplo: {$nin: ["XML","MongoDB"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

> db.usuarios.find( { ejemplo: {$nin: ["XML"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "C#", "SQL", "Java" ] }

> var dos = {nombre:"dos", ejemplo: ["XML", "Go"]}

> db.usuarios.insert(dos)

WriteResult({ "nInserted" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d54f166d23c3f65e31e5ec"), "nombre" : "Eduardo", "ejemplo" : [ "MongoDB", "C#", "SQL", "Java", "Python" ] }
{ "_id" : ObjectId("58d550f16d23c3f65e31e5ed"), "nombre" : "dos", "ejemplo" : [ "XML", "Go" ] }

> db.usuarios.find( { ejemplo: {$in: ["C#"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "C#", "SQL", "Java" ] }

> db.usuarios.find( { ejemplo: {$nin: ["C#"]}  }, {_id:false, nombre:false,ejemplo: {$slice:[ 1,3]  } })

{ "ejemplo" : [ "Go" ] }

> db.usuarios.update({ _id: ObjectId("58d54f166d23c3f65e31e5ec") },{$push: {ejemplo: "Go"} })

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.usuarios.find()

{ "_id" : ObjectId("58d54f166d23c3f65e31e5ec"), "nombre" : "Eduardo", "ejemplo" : [ "MongoDB", "C#", "SQL", "Java", "Python", "Go" ] }
{ "_id" : ObjectId("58d550f16d23c3f65e31e5ed"), "nombre" : "dos", "ejemplo" : [ "XML", "Go" ] }

> db.usuarios.find( { ejemplo: {$in: ["Go"]}  }, {} )

{ "_id" : ObjectId("58d54f166d23c3f65e31e5ec"), "nombre" : "Eduardo", "ejemplo" : [ "MongoDB", "C#", "SQL", "Java", "Python", "Go" ] }
{ "_id" : ObjectId("58d550f16d23c3f65e31e5ed"), "nombre" : "dos", "ejemplo" : [ "XML", "Go" ] }

