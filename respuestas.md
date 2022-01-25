Ejercicios MongoDB

Repositorio: https://github.com/Formate-con-Altia/practica-consultas-mongodb
Soluciones

ENCONTRAR - base de datos sample_restaurants, en la coleccion de restaurant

use sample_restaurants;

db.restaurants.find({ cuisine: "American" });
db.restaurants.find({ borough: "Queens" });
db.restaurants.find({ name: "Cafe Espanol" });
db.restaurants.find({ name: { $regex: /Cafe/ } });
db.restaurants.find({ "address.building": "41" });
db.restaurants.find({ "address.building": { $in: ["41", "66"] } });

ENCONTRAR - base de datos sample_mflix, en la coleccion de 'movies'

use sample_mflix;

db.movies.find({ year: { $lt: 1917 } });
db.movies.find({ }, { title: 1, _id: 0 });
db.movies.find({ year: { $lt: 1912 } }, { title: 1, _id: 0 });
db.movies.find({ genres: { $all: ["Short", "Romance", "Animation"] } });
db.movies.find({ rated: { $exists: true } });
db.movies.find({ rated: { $eq: "G",  $exists: true } });

BORRAR - base de datos sample_mflix, en la coleccion de 'movies'

use sample_mflix;

db.movies.find({ "imdb.rating": { $lt: 5 } });
db.movies.remove({ "imdb.rating": { $lt: 5 } });
