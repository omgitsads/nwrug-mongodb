!SLIDE

## Indexes

!SLIDE

## Add Indexes

    @@@javascript
    > db.events.ensureIndex({name: 1})
    > db.events.ensureIndex({tags: -1})
    > db.events.ensureIndex({
      "comments.user": 1
    })
    > db.events.ensureIndex({attendees: 1},
      {background: true})
    > db.events.ensureIndex({name: 1},
      {unique: true})
    > db.events.ensureIndex({
      name: 1, attendees: -1
    })
    
!SLIDE    

## Remove Indexes

    @@@javascript
    > db.events.dropIndex({name: 1})
    > db.events.dropIndexes()

!SLIDE

## Give me a hint!
    
    @@@javascript
    > db.events.find(
      {tags: "ruby"}
    ).hint({tags: -1})
    
!SLIDE

## Geospatial Indexes

### Add a location to my event

    @@@javascript
    > db.events.update(
      {name: "NWRUG - MongoDB is Awesome!"}, 
      {$set: {loc: [53.47405,-2.238657]}}
    )

### Add a 2D Index

    @@@javascript
    > db.events.ensureIndex({loc: "2d"})

!SLIDE

## Find My Events!

    @@@javascript
    > db.events.find({
      loc: {
        $near: [53.474038,-2.242005]
      }
    })
    > db.events.find({loc: {
      $within: {
        $box: [
          [53.47041,-2.246404],
          [53.477377,-2.231072]
        ]
      }
    }})