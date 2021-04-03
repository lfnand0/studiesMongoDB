# Chapter 3: Schemas & Relations: How to Structure Documents

## What's inside this Module?
* Understanding Document Schemas & Data Types
* Modelling Relations
* Schema Validation

## Schema-less or Not?
* MongoDB does NOT enforce schemas! Documents don't have to use the same schema inside of one collection
* But that does not mean that you can't use some kind of schema!

## Data Types
* Text
* Boolean
* Numbers
  * Integer (int32)
  * NumberLong (int64)
  * NumberDecimal
* ObjectId
* ISODate
* Timestamp
* Embedded Document
* Array

## Data Schemas & Data Modelling
* Which Data does my App need or generate?
  * Defines the Fields you'll need (and how they relate)
* Where do I need my data?
  * Defines your required collections + field groupings
* Which kind of Data or Information do I want to display?
  * Defines which queries you'll need
* How oftend do I fetch my data?
  * Defines whether you should optimize for easy fetching
* How often do I write or change my data?
  * Defines whether you should optimize for easy writing

## Relations - Options