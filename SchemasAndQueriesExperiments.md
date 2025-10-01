## Schemas and queries experiments

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
    "required": ["_from", "_to"],
    "additionalProperties": false
  },
  "level": "strict",
  "message": "Each ownership edge must connect an owner to a car. 'since' is optional, and 'endDate' must be a valid ISO date string if present."
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

