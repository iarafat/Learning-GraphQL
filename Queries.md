## 1

```
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
