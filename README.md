### objection.js
---
https://github.com/Vincit/objection.js

```js
const person = await Person.query().findById(1)

await Person.query().insert({ firstName: 'Jennifer' })

await Person
  .query()
  .patch({ firstName: 'Jennifer' })
  .whereIn('id', [1, 2, 3, 4])

const person = await Person
  .query()
  .findById(1)
  .eager({
    children: {
      pets: true,
      children: true
  }
})

console.log(person.children[0].pets[1].name)

const people = await Person
  .query()
  .where('lastName', 'Doe')
  .whereExists(
    Pet.query()
      .where('ownerId', ref('people.id'))
      .where('name', 'Fluffy')
  )
  .orderBy('firstName')

const insertedGraph = await Person
  .query()
  .insertGraph({
    firtName: 'Jennifer',
    lastName: 'Doe',
    
    children: [
      {
        firstName: 'Jack',
        lastname: 'Doe',
        
        pets: [
          {
            name: 'Fluffy'
          }
        ]
      }
    ]
  })
```

```
```

```
```


