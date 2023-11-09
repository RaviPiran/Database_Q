**01.Create a Database called movies.**

test> use Movies
switched to db Movies
Movies>


 **02.Create a collection called moviedetails.**
 
 db.createCollection("moviedetails")

**03.Create above 5 movie documents into a moviedetails collection.**

Movies> db.moviedetails.insertMany([{ "Movie-Title": "Jurassic Park", "Genre/Type": "Adventure" , "Director": "Steven Spielberg" , "Release Year": 1993 },{ "Movie-Title": "Forrest Gump", "Genre/Type": "Drama" , "Director": "Robert Zemeckies" , "Release Year": 1994 }, { "Movie-Title": "Titanic", "Genre/Type": "Romance", "Director": "James Cameron", "Release Year": 1997 }, { "Movie-Title": "The Dark Knight", "Genre/Type": "Action", "Director": "Christopher Nolan", "Release Year": 2008 },{ "Movie-Title": "Avatar", "Genre/Type": "Science Fiction", "Director": "James Cameron", "Release Year": 2009 }])

**04.List all documents created.**

Movies> db.moviedetails.find({})
[
  {
    _id: ObjectId("654c88cda1791bba19b7e117"),
    'Movie-Title': 'Jurassic Park',
    'Genre/Type': 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': 1993
  },
  {
    _id: ObjectId("654c88cda1791bba19b7e118"),
    'Movie-Title': 'Forrest Gump',
    'Genre/Type': 'Drama',
    Director: 'Robert Zemeckies',
    'Release Year': 1994
  },
  {
    _id: ObjectId("654c88cda1791bba19b7e119"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': 1997
  },
  {
    _id: ObjectId("654c88cda1791bba19b7e11a"),
    'Movie-Title': 'The Dark Knight',
    'Genre/Type': 'Action',
    Director: 'Christopher Nolan',
    'Release Year': 2008
  },
  {
    _id: ObjectId("654c88cda1791bba19b7e11b"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]

**05.List James Cameron’s movie**

Movies>db.moviedetails.find({ "Director": "James Cameron" })
[
  {
    _id: ObjectId("654c88cda1791bba19b7e119"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': 1997
  },
  {
    _id: ObjectId("654c88cda1791bba19b7e11b"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]

**06.List  James Cameron’s movies released in 2009.**

Movies> db.moviedetails.find({ "Director": "James Cameron", "Release Year": 2009 })
[
  {
    _id: ObjectId("654c88cda1791bba19b7e11b"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]


**07.Delete the movie which you don’t like.**

Movies> db.moviedetails.remove({"Director": "James Cameron"}) 
DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 2 }
Movies> 


**08.Add the movie which is your favourite.**

Movies> db.moviedetails.insertOne({"Movie-Title": "Leo", "Genre/Type": "Action" , "Director": "Lokesh" , "Release Year": 2023})
{
  acknowledged: true,
  insertedId: ObjectId("654c9fd7a1791bba19b7e11c")
}

**09.List movie Directed  by Christopher Nolan in 1994.**

Movies> db.moviedetails.find({ "Director": "Christopher Nolan", "Release Year": 1994 })


**10.List out the Director’s Name in your document.**

Movies> db.moviedetails.distinct("Director")
[
  'Christopher Nolan',
  'Lokesh',
  'Robert Zemeckies',
  'Steven Spielberg'
]

