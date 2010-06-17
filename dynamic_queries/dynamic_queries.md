!SLIDE

## Dynamic Queries

!SLIDE

## Find a Document!

    @@@javascript
    > db.events.find();
    > db.events.find({
      name : "NWRUG - MongoDB is Awesome!"
    });
    > db.events.find({
      tags : {$in : ["mongodb", "ruby"]}
    });
    > db.events.find({
      attendees : {
        $gt : 10
      }
    });

!SLIDE center smbullets

## Query Operators

* $lt
* $gt
* $lte
* $gte
* $ne
* $in
* $nin

!SLIDE center smbullets

## More Query Operators

* $mod
* $all
* $size
* $exists
* $type
* $elemMatch
* $not

!SLIDE

## Find by embedded document
  
### Dot Notation
  
    @@@javascript
    > db.events.find({
      "comments.user" : "@willj"
    });
    > db.events.find({
      "comments.0.user" : "@willj"
    });

!SLIDE

## Find by embedded document

### Sub Documents

    @@@javascript
    // This will not find our document!
    > db.events.find({
      comments : {
        user : "@adamholt"
      }
    });
    // This will!
    > db.events.find({
      comments : {
        user : "@adamholt", 
        comment : "I <3 MongoDB!"
      }
    });

### Sub Document matching only works on exact matches

!SLIDE

## A Word about $elemMatch

### $elemMatch will match the entire document within an array

    @@@javascript
    > db.events.find({
      "comments.user" : "@spammer",
      "comments.comment" : /^viagra/i
    });
    
    > db.events.find({
      comments : {
        $elemMatch : {
          user : "@spammer",
          comment : /^viagra/i
        }
      }
    });
    
!SLIDE
  
## Counting, Skipping and Limiting
  
    @@@javascript
    > db.events.find().sort({attendees : 1});
    > db.events.find().sort({attendees : 1});
    > db.events.find().limit(10);
    > db.events.find().skip(10);
    > db.events.find().count();
