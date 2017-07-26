## Wildlife Tracker

An app for the forest service to track animals for an environmental impact study.

### Description

The Forest Service is considering a proposal from a timber company to clearcut a nearby forest of Douglas Fir. Before this proposal may be approved, they must complete an environmental impact study. This application was developed to allow Rangers to track wildlife sightings in the area.

##Changes Included and Bugs Fixed

* Changed Animal class as an abstract class and inherit Animal class to the EndangeredAnimal class.
* Added both endangered and normal animals to a single table instead of two tables to make sure we do not have any issues with IDs in the sightings table.
* Included a boolean field called isEndangered in the animal table to differentiate between animals and endangered animals.
* Included a timestamp field called time in the Sightings class.
* Changed the method all() to allEndangeredAnimals() in the EndangeredAnimal class and tested them.
* Reviewed routes and checked the values that are passing through and passed individual animal objects instead of a list of endangered animals.

### Setup

To create the necessary databases, launch postgres, then psql, and run the following commands:

* `CREATE DATABASE wildlife_tracker;`
* `\c wildlife_tracker;`
* `CREATE TABLE animals (id serial PRIMARY KEY, name varchar, isEndangered boolean);`
* `CREATE TABLE endangered_animals (id serial PRIMARY KEY, name varchar, health varchar, age varchar, isEndangered boolean);`
* `CREATE TABLE sightings (id serial PRIMARY KEY, animal_id int, location varchar, ranger_name varchar, date timestamp);`
* `CREATE DATABASE wildlife_tracker_test WITH TEMPLATE wildlife_tracker;`

### License

Copyright (c) 2017 **_MIT License_**
