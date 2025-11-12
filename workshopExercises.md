### Version 1
### Over-all scenario

Buying a second-hand car can, at first, be a daunting task; listings only offer a summary of the information about the vehicle and it can be hard to obtain more information out of the seller, especially the negative type like accidents or issues the car has.
Fortunately, in many countries nowadays you can find details about a car's history via either their license plate or VIN number with the help of websites like https://www.kentekencheck.nl/ . A report from such websites includes everything regarding the car's history, from periodic technical inspections, mileage, accident history, repairs and recalls done, if the car has been imported from another country etc.
For this series of exercises, we will be creating a database for such a service.

#### Exercises

1. Create a database with three collections:
 - owner (document collection);
 - car (document collection);
 - carOwnership (edge collection); 

2. Create and enforce schemas for each collection: (move to different, more advanced exercise?)
 - 
 - **Attention!** In edge collections, the "_from" and "_to" fields also have to be defined as part of the schema.

3. Insert multiple entries into these collections (around 3-6 for each).
 - **Note** It is possible for one person to own multiple cars.
 - **Note** It is possible that one car has had more than one owner.

 split into multiple exercises?(6?)
 start with very simple, move towards complexity



#### Version 2

### Introduction

For this set of exercises, we will be creating a database for car ownership history.

#### Exercises

1. Create a new database and user.
 - Give the new user **Administrate** rights over this new database and **No access** for default option. Log in to the new database with this user for the following exercises.

2. Add three collections:
 - owner (document collection);
 - car (document collection);
 - carOwnership (edge collection, from owner to car); 

3. Insert multiple entries into these collections (around 5-10 for each).
Attributes for each collection:
 - owner: firstName, lastName, age;
 - car: brand, model, color, dateOfFirstRegistration;
 - carOwnership: beginDate (mandatory), endDate (optional, if car is still being owned by a particular owner)

 - **Note** It is possible for one person to own multiple cars.
 - **Note** It is possible for one car to have had more than one owner over its life.

4. Create a **GeneralGraph** with the collections made before as its parameters.

5. Run some basic queries for selecting, deleting based on an attribute, inserting new entries.

6. Create and enforce schemas for each collection: (move to different, more advanced exercise?)
 - 
 - **Attention!** In edge collections, the "_from" and "_to" fields also have to be defined as part of the schema.