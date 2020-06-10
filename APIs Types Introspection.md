
### 1

```graphql

query InterfaceTypes {
  __type(name: "Pet") {
    kind
    name
    description
    possibleTypes {
      name
      kind
      description
    }
  }
}


query AvailableQueries {
  __schema {
    queryType  {
      fields {
        name
        description
      }
    }
  }
}

query Customer {
  __type(name: "Customer") {
    fields{
      name
      description
    }
  }
}

query AllTypes {
  __schema {
    types {
      name
      kind
      description
    }
  }
}

```
