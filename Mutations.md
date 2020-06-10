### 1

```graphql

mutation {
  createAccount(
    input: { name: "Arafat", username: "iarafat", password: "pass" }
  ) {
    username
    name
  }
}

```


### 2

```graphql

mutation CheckIn {
  checkIn(id: "C-7") {
    pet {
      name
    }
    checkOutDate
    checkInDate
    late
  }
}

mutation CheckOut {
  checkOut(id: "C-7") {
    pet {
      name
    }
    customer {
      name
    }
  }
}

mutation LogIn {
  logIn(username: "iarafat", password: "pass") {
    customer {
      name
    }
    token
  }
}

```

#### 2.1
##### HTTP HEADERS
```josn

{
  "Authorization": "Bearer token"
}

```
