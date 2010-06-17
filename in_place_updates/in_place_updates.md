!SLIDE

## In-place Updates

!SLIDE

## Update

    @@@javascript
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      { 
        "name" : "NWRUG - MongoDB is Awesome!",
        "tags" : [
          "mongodb", 
          "ruby", 
          "nwrug", 
          "awesome"
        ],
        "attendees" : 25,
      }
    );
    
!SLIDE

## Upsert

    @@@javascript
    > db.events.update(
      { name: "NWRUG - MacRuby by Caius?"},
      { 
        "name" : "NWRUG - MacRuby by Caius?",
        "tags" : [
          "mac", 
          "ruby", 
          "nwrug", 
          "macruby"
        ],
        "attendees" : 25,
      },
      true
    );
    
!SLIDE

## Modifier Operations

    @@@javascript
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$inc: {attendees: 1}}
    );
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$dec: {attendees: 1}}
    );
    
!SLIDE

## More Modifier Operations
    
    @@@javascript
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$set: {speaker: "Adam Holt"}}
    );
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$unset: {attendees: 1}
    );
    
!SLIDE

## More Modifier Operations

    @@@javascript
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$push: {tags: "mongoid"}}
    );
    > db.events.update(
      { name: "NWRUG - MongoDB is Awesome!"},
      {$pull: {tags: "awesome"}}
    );

!SLIDE

## Positional Operator


    @@@javascript
    > db.events.update(
      {"comments.user": "@adamholt"},
      {$inc : {"comments.$.votes" : 1}}
    );