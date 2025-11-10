## Over-all scenario

Buying a second-hand car can, at first, be a daunting task; listings only offer a summary of the information about the vehicle and it can be hard to obtain more information out of the seller, especially the negative type like accidents or issues the car has.
Fortunately, in many countries nowadays you can find details about a car's history via either their license plate or VIN number with the help of websites like https://www.kentekencheck.nl/ . A report from such websites includes everything regarding the car's history, from periodic technical inspections, mileage, accident history, repairs and recalls done, if the car has been imported from another country etc.
For this series of exercises, we will be creating a database for such a service.

#### Exercise 1

1. Create a database with three collections:
 - owner;
 - car;
 - car ownership (edge collection); 

2. Create and enforce schemas for each collection.
 - **Attention!** In edge collections, the "_from" and "_to" fields also have to be defined as part of the schema.

3. Insert multiple entries into these collections (around 10-20 for each).
 - **Note** It is possible for one person to own multiple cars.
 - **Note** It is possible that one car has had more than one owner.