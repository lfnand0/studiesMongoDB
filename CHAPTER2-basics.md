# Chapter 2: Understanding the Basics & CRUD Operations

## CRUD Operations
    * Create
        * insertOne(data, options)
        * insertMany(data, options)
            * USAGE:
                * with insertMany, we have to add a JSON document, such as ./01-flights.json
                * db.flightData.insertMany([
                    {
                        "departureAirport": "MUC",
                        "arrivalAirport": "SFO",
                        "aircraft": "Airbus A380",
                        "distance": 12000,
                        "intercontinental": true
                    },
                    {
                        "departureAirport": "LHR",
                        "arrivalAirport": "TXL",
                        "aircraft": "Airbus A320",
                        "distance": 950,
                        "intercontinental": false
                    }
                ])
    * Read
        * find(filter, options)
            * db.flightData.find(), which prints every document
            * we can find specific documents by doing the following:
                * db.flightData.find({intercontinental: true}), which prints every doc with intercontinental = true
            * we can also find, for example, documents that have distance: greater than a certain value
                * db.flightData.find({distance: {$gt: 10000}})
                * NOTE: $gt stands for greather than, there is also $lt which is less than
        * findOne(filter, options)
            * pretty much the same usage as find()
        * NOTE: we can use .pretty() after find or findOne to format it in a more digestable way
    * Update
        * update(filter, data, options)
            * USAGE:
                * we can change a value inside the document with it
                * db.flightData.updateOne({_id: ObjectId("605f4d033f67aeac9fb2dd28")}, {$set: {delayed: false}})
                    * changes the value of delayed: from the document with _id: ... from true to false
                * NOTE: if you DON'T use {$set: {NEW OBJECT}}, and instead just use {NEW OBJECT} in the second argument, you replace the whole object with {NEW OBJECT}
        * updateOne(filter, data, options)
            * USAGE:
                * db.flightData.updateOne({distance: 12000}, {$set: {marker:'delete'}})
                * adds marker: 'delete' to the first document that has distance: 12000
                * NOTE: remember to use {$set: } in the second argument
        * updateMany(filter, data, options)
            * USAGE:
                * db.flightData.updateMany({}, {$set: {marker: "toDelete"}})
                * in this case, it adds marker: "toDelete" to ALL documents inside flightData
        * replaceOne(filter, data, options)
    * Delete
        * deleteOne(filter, options)
            * USAGE:
                * db.flightData.deleteOne({departureAirport: "TXL"})
                * deletes the first document with departureAirport: "TXL" inside the collection flightData
        * deleteMany(filter, options)
            * USAGE:
                * to delete all, we can use: 
                    * db.flightdata.deleteMany({})
                * to delete specific documents, we can use:
                    * db.flightData.deleteMany({marker: "toDelete"})
                    * this deletes every document that has marker: "toDelete"

## Cursor
    * .find() only returns 20 objects
    * to print the whole collection, we have to use:
        * db.passengers.find().toArray()
        * db.passengers.find().forEach((passengerData) => {printjson(passengerData)})

## Projection
    * db.passengers.find({}, {name: 1}).pretty()
        * in this case, it excludes everything but the name and the _id
        * to exclude the id and print only the name, we use:
            * db.passengers.find({}, {name:1, _id: 0}).pretty()

## Accessing Structure Data
    * We can add arrays inside documents
    * To access those arrays, we can use:
        * db.passengers.findOne({name: "Albert Twostone"}).hobbies
        * NOTE: since we're accessing one specific array "hobbies", we have to use findOne() and NOT find()

## Module Summary
    * Databases, Collections, Documents
        * A Database holds multiple Collections, where each Collection can then hold multiple Documents
        * Databases and Collections are created "lazily" (i.e. when a Document is inserted)
        * A Document can't directly be inserted into a Database, you need to use a Collection!
    * Document Structure
        * Each document needs a unique ID (and gets one by default)
        * You may have embedded documens and array fields
    * CRUD Operations
        * CRUD = Create, Read, Update, Delete
        * MongoDB offers multiple CRUD operations for single-document and bulk actions (e.g. insertOne(), insertMany(), ...)
        * Some methods require an argument (e.g. insertOne()), but others don't (e.g. find())
        * find() returns a cursor, NOT a list of documents!
        * Use filters to find specific documents
    * Retrieving Data
        * Use filters and operators (e.g. $gt) to limit the number of documents you retrieve
        * Use projection to limit the set of fields you retrieve