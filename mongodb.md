# What is MongoDB?
    * Database solution
    * The name stems from 'Humongous', since it can store a LOT of data

## How does it work?
    * Database
        * Collections
            * Documents (uses BSON (JSON converted to binary) data format: similar to objects from JS)
                * SCHEMALESS: does not require a rigid, pre-defined schema like a relational database
                * Because of this, the way mongoDB works is way less strict than relational databases and is, therefore, more flexible   
                
    * It works through collections (differently than in the SQL world, which works through tables)

## BSON Data Structure
    * No Schema
    * No / Few Relations
    
## MongoDB Ecosystem
    * MongoDB Database
        * Self-Managed / Enterprise versions
            * CloudManager / OpsManager
        * Atlas (Cloud)
        * Mobile
        * Compass (graphical user interface)
        * BI Connectors
        * MongoDB Charts
    * Stitch (Serverless Backend solution)
        * Serverless Query API
        * Serverless Functions
        * Database Triggers
        * Real-Time Sync

## First Use
    * After having a server set-up and running, we can use:
        * show dbs (prints out the available databases)
        * use [DATABASE-NAME] (this works even with databases that don't exist yet, which will be added once they have data in them)
        * db.[COLLECTION-NAME].insertOne({JSON-OBJECT}) (creates a collection)
        * db.[COLLECTION-NAME].find() (prints out the documents inside the collection)
            * db.[COLLECTION-NAME].find().pretty()
        * etc.

## Course Outline
    * Introduction
    * Basics & Basic CRUD           (NEWCOMERS)
    * Data Schema & Relations
    * Working with the Shell
    * Using Compass
    * CRUD Deep Dive - Create       (BASIC)
    * CRUD Deep Dive - Read
    * CRUD Deep Dive - Update
    * CRUD Deep Dive - Delete
    * Using Indexes                 (ADVANCED)
    * Working with Geospatial Data
    * The Aggregation Framework
    * Working with Numeric Data
    * Security & Authentication
    * Performance, Fault Tolerance & Deployment
    * Transactions
    * From Shell to Drivers
    * MongoDB Stitch                (COURSE END)

## How to get the most out of the course
    * Watch the videos at your pace
    * Pause & code along
        * Active > Passive
    * Do the sssignments
    * Dive into the Official Docs + Google
        * Learn to solve problems