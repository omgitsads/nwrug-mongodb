!SLIDE title center

# Embedded Documents

!SLIDE

## Create a document

    @@@javascript
    > db.events.insert({
      name : "NWRUG - MongoDB is Awesome!",
      tags : ["mongodb", "ruby", "nwrug"],
      attendees : 25,
      comments : [{
          user : "@willj",
          comment : 
            "I'm gonna use MongoDB for all my 
            projects! Screw Postgres!"
        },
        {
          user : "@adamholt",
          comment : "I <3 MongoDB!"
      }]
    });