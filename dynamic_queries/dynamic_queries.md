!SLIDE

## Dynamic Queries

!SLIDE

## Find a Document!

    @@@javascript
    db.events.find();
    db.events.find({
      "name" : "NWRUG - MongoDB is Awesome!"
    });
    db.events.find({
      "tags" : {"$in" : ["mongodb", "ruby"]}
    });
    db.events.find({
      "attendees" : {
        "$gt" : 10
      }
    });