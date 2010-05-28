!SLIDE

# Getting Started #

!SLIDE commandline incremental

# Install! #

    $curl http://downloads.mongodb.org/osx/mongodb-osx-i386-1.4.3.tgz > mongodb-osx-i386-1.4.3.tgz
    $tar -xzvf mongodb-osx-i386-1.4.3.tgz
    $mkdir -p /data/db # create the mongodb data dir
    $cd mongodb-osx-i386-1.4.3
    $./bin/mongod # start mongodb

!SLIDE

# Create a Document! #

    @@@javascript
    db.events.insert({
      "name" : "NWRUG - MongoDB is Awesome!",
      "tags" : ["mongodb", "ruby", "nwrug"],
      "attendees" : 25
    });