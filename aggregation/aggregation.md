!SLIDE

## Aggregation

!SLIDE

## Grouping

    @@@javascript
    > db.events.group({
      key: {speaker: true},
      inital: {count: 0},
      reduce: function(doc, prev){
        prev.count++;
      }
    });
    
    // Result
    [{
      "speaker": "Adam Holt",
      "count": 1
    }]

!SLIDE

## MapReduce

    @@@javascript
    > map = function(){
      this.tags.forEach(
        function(tag){
          emit( tag , { count : 1 } );
        }
      );
    }
    > reduce = function(key, values){
      var total = 0;
      for(var i=0;i<values.length;i++)
        total += values[i].count;
      return {count: total};
    }
    > res = db.events.mapReduce(map, reduce);
    
!SLIDE

## MapReduce Results

    @@@javascript
    {
      "result": "tmp.mr.mapreduce_1276726664_3",
      "timeMillis": 90,
      "counts": {
        "input": 1,
        "emit": 4,
        "output": 4
      },
      "ok" : 1,
    }

!SLIDE    

## Getting the results
    
    @@@javascript
    > db[res.result].find()
    { 
      "_id": "mongodb", 
      "value": { "count" : 1 } 
    }
    { 
      "_id": "mongoid", 
      "value": { "count" : 1 } 
    }
    { 
      "_id": "nwrug", 
      "value": { "count" : 1 } 
    }
    { 
      "_id": "ruby", 
      "value": { "count" : 1 } 
    }
    