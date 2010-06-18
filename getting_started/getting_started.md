!SLIDE

# Getting Started #

!SLIDE commandline incremental

# Install! #

    $ curl http://downloads.mongodb.org/osx/mongodb-osx-i386-1.4.3.tgz > mongodb-osx-i386-1.4.3.tgz
    $ tar -xzvf mongodb-osx-i386-1.4.3.tgz
    $ mkdir -p /data/db # create the mongodb data dir
    $ ./mongodb-osx-i386-1.4.3/bin/mongod # start mongodb

!SLIDE commandline

# Mongo Console #

    $ ./mongo-osx-i386-1.4.3/bin/mongo

!SLIDE smbullets

# Terminology #

* Database == Database
* Collection == Table
* Document == Row

!SLIDE smbullets

# Document Storage #

## BSON ##

* Binary Serialization of JSON-like Documents
* Fast to Encode, Decode and Traverse
* Extra Data Types

!SLIDE

# Setup your Database #

    @@@javascript
    > use nwrug-mongodb
    switched to db nwrug-mongodb

!SLIDE
# Create a Document! #

    @@@javascript
    > db.events.insert({
      name : "NWRUG - MongoDB is Awesome!",
      tags : ["mongodb", "ruby", "nwrug"],
      attendees : 25
    });