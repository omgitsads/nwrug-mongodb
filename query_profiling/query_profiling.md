!SLIDE

## Query Profiling

    @@@javascript
    > db.events.find({tags: "ruby"}).explain();

!SLIDE
    
    @@@javascript
    {
      "cursor" : "BasicCursor",
      "indexBounds" : [ ],
      "nscanned" : 1,
      "nscannedObjects" : 1,
      "n" : 1,
      "millis" : 22,
      "oldPlan" : {
        "cursor" : "BasicCursor",
        "indexBounds" : [ ]
      },
      "allPlans" : [
        {
          "cursor" : "BasicCursor",
          "indexBounds" : [ ]
        }
      ]
    }