# Spring-boot with mongodb crud operations using intlej
```
=>added dependency: mongojavadriver ,spring web
=>for creating the maven starter.spring.io
=>connected through the mongodb
```

# MongoDb:


=>creating the database and collections

- for creating the collections
```
db.createCollections('nexwave')
```

- inserting the one user
```
db.nexwave.insertOne({'_id':1,'name':'Raj','age':23,'gender':'male','address':'chaitnyapuri','email':'raj@gmail.com'})
```
- inserting many user at a time
```
db.nexwave.insertMany([{'_id':2,'name':'nikhil','age':24,'gender':'male','address':'karimnagar','email':'nikki@gmail.com'},{'_id':3,'name':'mounika','age':25,'gender': 'female',
  'address': 'bcm',
  'email': 'mouni@gmail.com'}])
 ```
  - finding the  all users

```
  db.nexwave.find({})
```
- finding particular user
```
 db.nexwave.findOne({'_id':3})
```
- finding using insert(depricated instead of Collection.insert() is deprecated. Use insertOne, insertMany, or bulkWrite. )
    - bulkWrite only supports insertOne, updateOne, updateMany, deleteOne, deleteMany

```
db.nexwave.insert([{_id:4,name:'pranay',age:'23',gender:'male',address:'nagole',email:'pranay@gmail.com'},{_id:5,name:'praveen',age:27,gender:'male', 
  address: 'uppal',
  email: 'praveen@gmail.com' }
 ```
 - ordered false will help us not to be in ordered
 ```
 db.nexwave.insertOne({'_id':9,name:'lucky',
 age:25,gender:'male',address:['pune','hyd'],email:'lucky@gmail.com'},{ordered:false
 ```

 - for getting all users
 ```
 db.nexwave.find() or db.nexwave.find({})
 ```
 - for getting one user
 ```
db.nexwave.findOne()
if we dont specify any thing by default it will take the first
 ```
 - for getting by name

 ```
 db.nexwave.find({name:'Raj'})
 ```
 - for getting document in pretty way
 ```
 db.nexwave.find().pretty()
 ```
 - for counting the documents
 ```
 db.nexwave.countDocuments()
 ```
 - for counting fields
    - 'DeprecationWarning: Collection.count() is deprecated. Use countDocuments or estimatedDocumentCount.'

- for counting specific field
 ```
 db.nexwave.count({age:25})

 ```
 - for unique 
 ```
 db.nexwave.distinct("name")
 ```
 - using or

 ```
 db.nexwave.find(
  {$or :
  [
    {name :'Raj'},
    {age:25}
    ]
    
  })
  ```
  - using and
  ```
  db.nexwave.find({$and:[{address:'pune'},{name:'lucky'}]})
  ```
  - greater than
  ```
  db.nexwave.find({age: {$gt:19}})
  ```
  - greater than
  ```
  db.nexwave.find({age: {$gte :26}})

  ```
  - lessthan
  ```
  db.nexwave.find({age:{$lt :24}})
  ```
  - lessthan equal

  ```
  db.nexwave.find({age:{$lte:25}})
  ```
  - $in it will check whether it is in collection or not
  ```
  db.nexwave.find({age:{$in:[23,25]}})
  ```
  - $nin it will give the which are not in the collection
  ```
  db.nexwave.find({age:{$nin:[12,21]}})
  ```
  - $nin it will give the which are not in collection
  ```
  db.nexwave.find({age:{$nin:[23]}})
  ```