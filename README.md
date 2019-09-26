# star_wars_census
Sample application that allows a user to see the list of all planets and people of star-wars. 

` return people and their plannets.`

```query {
  peopleList {
    edges {
      node {
        id
        name
        height
        mass
        hairColor
        skinColor
        eyeColor
        birthYear
        gender
        created
        edited
        url
        planet {
          id
          name
          rotationPeriod
          diameter
          climate
          gravity
          terrain
          surfaceWater
          population
          created
          edited
          url
        }
      }
    }
  }
}
```

`Return one planet and its people` 

``` query {
  planet (id: "UGxhbmV0OjE="){
    id
    name
    rotationPeriod
    diameter
    climate
    gravity
    terrain
    surfaceWater
    population
    created
    edited
    url
    peopleList {
      edges {
        node {
          id
          name
          height
          mass
          hairColor
          skinColor
          eyeColor
          birthYear
          gender
          created
          edited
          url
        }
      }
    }
  }
} ```


`Create a person` 

``` 

mutation {
  createPerson (input: {
    name: "Alexis ROLLAND"
    height: "189"
    mass: "73"
    hairColor: "brown"
    skinColor: "white"
    eyeColor: "green"
    birthYear: "1984"
    gender: "male"
    planetId: "UGxhbmV0Ojk="
  }) {
    person {
      id
      name
      height
      mass
      hairColor
      skinColor
      eyeColor
      birthYear
      gender
      planet {
        id
        name
      }
      created
      edited
      url
    }
  }
}
```

`update a planet ` 

```
mutation {
  updatePlanet (input:{
    id: "UGxhbmV0Ojk="
    population: "1000000000001"
  }) {
    planet {
      id
      name
      rotationPeriod
      orbitalPeriod
      diameter
      climate
      terrain
      surfaceWater
      population
      created
      edited
      url
    }
  }
}
```
