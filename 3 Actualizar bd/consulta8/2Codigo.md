db.Movies.updateOne(
{ \_id:ObjectId('66b864a4add9612b18228fb9')},
{ $set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."} }
);

db.Movies.findOne({ \_id: ObjectId('66b864a4add9612b18228fb9') });
