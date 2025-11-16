### Introduction

Prerequisite: 
- have Docker running (Docker Dekstop makes it easier to track containers)
- have a container with arangoDB running (see docker_compose.yaml)
For this set of exercises, we will be creating a database for car ownership history.

#### Exercises 

1. Create a new database and user.
 - Give the new user **Administrate** permissions over this new database and **No access** for default option. Log out of the _root database (top-right of the screen, right next to username) Log in to the new database with this user for the following exercises.

2. Add three collections:
 - owner (document collection);
 - car (document collection);
 - carOwnership (edge collection, from owner to car); 

3. Insert multiple entries into these collections (around 5-10 for each) using web UI (click on collection -> contents -> green plus sign) or AQL queries.
Attributes for each collection:
 - owner: firstName, lastName, age;
 - car: brand, model, color, dateOfFirstRegistration;
 - carOwnership: _from (entry from owner collection), _to (entry from car collection) beginDate (mandatory), endDate (optional, if car is still being owned by a particular owner)

 - **Note** Make sure to specify the *_key* attribute to assign specific key values instead of auto-generated ones.
 - **Note** It is possible for one person to own multiple cars.
 - **Note** It is possible for one car to have had more than one owner over its life.

4. Create a **GeneralGraph** with the collections made before as its parameters and load the full graph.

5. Run some basic queries for selecting, deleting based on an attribute, inserting new entries.

6. Create a new document collection named "reports" for handling accident reports. Create a new edge collection called "involvedIn". Insert entries in such a way that a report is connected to both a car and its owner from their relevant collections. Create a new GeneralGraph showing their relationship.

7. Create and enforce schemas for each collection:
 - 
 - **Attention!** In edge collections, the "_from" and "_to" fields also have to be defined as part of the schema.



#### Cheat sheet


AQL Select

~~~
    FOR doc IN @@collection
        FILTER doc.`attribute` == @value
    RETURN doc
~~~

AQL Insert Multiple Entries

~~~
   FOR doc in [array]
   INSERT array in @@collection
~~~

AQL Remove

~~~
    FOR doc IN @@collection
        FILTER doc.`attribute` == @value
    REMOVE doc in @@collection
~~~