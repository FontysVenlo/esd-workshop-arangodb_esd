## Schemas and queries experiments

#### Short notes

_from and _to are special fields that should not be included in required fields list as it will lead to errors; it is fine to enforce field types and formats

additionalProperties has to be set to true for edge collections

#### carOwnership schema

{
  "rule": {
    "type": "object",
    "properties": {
      "_from": {
        "type": "string",
        "pattern": "^owners/.*"
      },
      "_to": {
        "type": "string",
        "pattern": "^cars/.*"
      },
      "since": {
        "type": "string",
        "format": "date"
      },
      "endDate": {
        "type": "string",
        "format": "date"  
      }
    },
    "additionalProperties": true
  },
  "level": "strict",
  "message": "Each ownership edge must connect an owner to a car. 'beginDate' and 'endDate are optional, and both' must be a valid ISO date string if present."
}

#### cars schema

{
  "rule": {
    "type": "object",
    "properties": {
      "make": { "type": "string" },
      "model": { "type": "string" },
      "year": { "type": "integer", "minimum": 1886 },
      "licensePlate": {
        "type": "string",
        "pattern": "^([A-Z]{2}-\\d{2}-\\d{2}|\\d{2}-\\d{2}-[A-Z]{2}|\\d{2}-[A-Z]{2}-\\d{2}|[A-Z]{2}-\\d{2}-[A-Z]{2}|\\d{2}-[A-Z]{2}-[A-Z]{2}|[A-Z]{2}-[A-Z]{2}-\\d{2}|[A-Z]{2}-[A-Z]{2}-[A-Z]{2})$"
      }
    },
    "required": ["make", "model", "year", "licensePlate"],
    "additionalProperties": false
  },
  "level": "strict",
  "message": "Each car must have a make, model, year, and a Dutch-format license plate (e.g., XX-99-99)."
}


#### owners schema

{
  "rule": {
    "type": "object",
    "properties": {
      "name": { "type": "string" },
      "age": { "type": "integer", "minimum": 0 }
    },
    "required": ["name", "age"],
    "additionalProperties": false
  },
  "level": "strict",
  "message": "Each owner must have a name and a non-negative age."
}


#### insert into owners

FOR owner IN [
  { _key: "owner1", name: "Alice", age: 34 },
  { _key: "owner2", name: "Jan", age: 47 },
  { _key: "owner3", name: "Stefan", age: 29 }
]
INSERT owner INTO owners

#### insert into cars

FOR car IN [
  { _key: "car1", make: "Volkswagen", model: "Golf", year: 2005, licensePlate: "AB-12-34" },
  { _key: "car2", make: "Toyota", model: "Yaris", year: 2011, licensePlate: "12-AB-34" },
  { _key: "car3", make: "Mazda", model: "MX-5", year: 2025, licensePlate: "CD-56-EF" }
]
INSERT car INTO cars

#### insert in carOwnership

FOR ownership IN [
  {
    _from: "owners/owner1",
    _to: "cars/car1",
    beginDate: "2005-05-05"
  },
  {
    _from: "owners/owner2",
    _to: "cars/car2",
    beginDate: "2011-03-03",
    endDate: "2025-01-01"
  },
  {
    _from: "owners/owner3",
    _to: "cars/car3"
    // no since or endDate — valid
  }
]
INSERT ownership INTO carOwnership

#### select from carOwnership

FOR ownership IN carOwnership
  RETURN ownership