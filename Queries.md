### 1

```graphql

query {
  available: totalPets(status: CHECKEDOUT)
  checkedout: totalPets(status: AVAILABLE)
  total: totalPets
  pets: allPets (status: CHECKEDOUT, category: CAT) {
    name
    weight
    status
    category
    petPhoto: photo {
      full
      thumb
    }
  }
}

```


### 2

```graphql

query($category: PetCategory=DOG, $status: PetStatus) {
  
   allPets (category: $category, status: $status) {
    id
    name
    status
    category
    inCareOf {
      name
    }
  }
}

```


### 3

```graphql

query {
  totalCustomers
  allCustomers {
    name
    username
    currentPets {
      name
    }
    checkoutHistory {
      pet {
        name
      }
      checkOutDate
      checkInDate
      late
    }
  }
  petById(id: "C-1") {
    name
    inCareOf {
      name
      username
    }
  }
}


```


### 4

```graphql

query PetsPage {
  available: totalPets(status: CHECKEDOUT)
  checkedout: totalPets(status: AVAILABLE)
  total: totalPets
  pets: allPets (status: CHECKEDOUT, category: CAT) {
    name
    weight
    status
    category
    petPhoto: photo {
      full
      thumb
    }
  }
}

query CustomersPage {
  totalCustomers
  allCustomers {
    name
    username
    currentPets {
      name
    }
  }
  petById(id: "C-1") {
    name
    inCareOf {
      name
      username
    }
  }
}

```


### 5

```graphql

query {
  petById(id: "C-1") {
    ...PetDetails
    inCareOf {
      ...CustomerDetails
    }
  }

  allPets(category: RABBIT, status: AVAILABLE) {
    ...PetDetails
  }
}

fragment CustomerDetails on Customer {
  name
  username
}

fragment PetDetails on Pet {
  name
  weight
  category
  photo {
    thumb
  }
}


```

# From funded pet library

### 6

```graphql

query PetsByType {
  allPets {
    id
    name
    __typename
    ... on Cat {
      sleepAmount
    }

    ... on Rabbit {
      favoriteFood
    }
  }
}

query PetsDetails {
  availablePets
  checkedOutPets
  totalPets
}

query CustomersDetails {
  totalCustomers
  customersWithPets {
    name
    username
  }
  allCustomers {
    dateCreated
    username
    name
  }
}


```
