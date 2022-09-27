# GraphQL Restaurant Exercise

This assignment was part of the course work required in the MIT xPRO Full-Stack development course. 

## Using GraphQL to query and update data

Creating multi-tier applications means building multiple API endpoints to handle different data operations. The more complex your application becomes, the harder it is to maintain all these endpoints. GraphQL aims to reduce this complexity by providing a simpler view of data and making it easier to query it. 

### Tasks

- Set up GraphQL for restaurant data
- Add mutations to get and update the data

### List of GraphQL queries used:

- restaurant: This gets a single restaurant based on a provided ID. 
- restaurants: This gets a list of all restaurants. 
- setrestaurant: This creates a new restaurant. 
- Deleterestaurant: This deletes a restaurant based on the provided id.
- editrestaurant: This updates a restaurant based on the provided id.

```javaScript
mutation editrestaurants($idd: Int = 1, $name: String = "OLDO") {
  editrestaurant(id: $idd, name: $name) {
    name
    description
  }
}

mutation setrestaurants {
  setrestaurant(input: {
    name: "Granite",
    description: "American",
  }) {
    name
    description
  }
}

mutation deleterestaurants($iid: Int = 1) {
  deleterestaurant(id: $iid) {
    ok
  }
}

query getrestaurants {
  restaurants {
    name
    description
    dishes {
      name
      price
    }
  }
}

query getrestaurant($iid: Int = 1) {
  restaurant(id:$iid){
    name
    description
  }
}
```

## Installation
- Clone or download all files into a directory
- From your terminal, run `npm install`
- Run the index.js file on `http://localhost:5500/graphql` in order to make queries with GraphQL


## License
[MIT](https://github.com/leahselig/GraphQL-Restaurant-Exercise/blob/main/LICENSE)
