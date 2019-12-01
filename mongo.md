# Mongo

## Nr 0

`docker pull mongo`

`docker run -d -p 27017-27019:27017-27019 --name mongodb mongo`

`docker exec -it mongodb bash`

`mongo`

Version checken --> `db.version()`

Hilfe --> `help`

## Nr 1

create db --> `use dbOfMax`

insert document --> `db.random.insert({ "val":1})`

get all inserted documents --> `db.random.find()`

get only the first two --> `db.random.find().limit(2)`

get where val is 2 --> `db.random.find({ "val":2 })`

update all with 4 to 5 --> `db.random.updateMany({ "val":4 }, {$set: { "val":5 }})`

show dbs --> `show dbs`

get collections for db --> `db.getCollectionNames()`

## Nr 2

insert random using _rand() --> `db.mycoll.insert({ "val": Math.floor(_rand() * (4 - 1 + 1)) + 1 })`

schleife --> `for (i = 0; i < 1000; i++) { db.mycoll.insert({ "val": Math.floor(_rand() * (4 - 1 + 1)) + 1 }) }`

show distribution --> `db.mycoll.aggregate([ { $group: { _id: "$val", total: { $sum: 1 } } } ])`