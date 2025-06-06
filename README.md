# examenMongo


2. Agregar Producto
db.products.insertOne({
"sku": "A101",
"name": "Figura Naruto Uzumaki",
"category": "Figuras",
"price": 120000,
"stock": 10,
"anime": "Naruto",
"rating": 4.8,
"tags": ["coleccionable", "resina", "edición especial"],
"provider": {
"name": "OtakuDistribuciones",
"country": "Japón"
}
})

3.
db.products.updateMany({}, {$set: {available: true, origin: "Importado"}})

4.
db.products.updateOne({sku: "A034"}, {$set: {stock: 15}})
db.products.updateOne({sku: "A018"}, {$set: {provider.country: "Colombia"}})

(No sabia como hacerlo asi que actualice todo el set a como estaba con lo que ya tenia) 
db.products.updateOne({sku: "A012"}, {$set: {tags: [
    'algodón',
    'edición limitada',
		'nuevo',
		'popular'  
]}})

(Al igual con este)
db.products.updateOne({sku: "A025"}, {$set: {tags: [
    'retro',
    'amarilla',
		'descuento',
		'outlet'
  ]})

db.products.updateOne({name: "Camiseta Goku Ultra Instinct"}, {$set: {price: 45000}})


5.
db.products.updateMany({}, {$rename: {"origin": "import_type"}})

6.
db.products.updateMany({"provider.country":"Colombia"},{$set: {import_type: "Nacional"}} )


7.
1. db.products.find({category: "Mangas"})
2. db.products.find({price: {$gt: 50000}})
3. db.products.find({category: {$ne: "Figuras"}})
4. db.products.find({category: {$ne: "Figuras"}})
5. db.products.find({category: {$ne: "Figuras"}})


8.
db.products.updateMany({}, {$unset: {avaliable: ""}})

9.
db.products.updateOne({sku: "A025"}, {$pull: {tags: "descuento"}})

10.
db.products.updateOne({sku: "A012"}, {$pull: {tags: {$in : ["nuevo", "popular"]}}})

11.
db.products.deleteOne({sku: "A043"})

12.
db.products.deleteMany({stock: 0})



