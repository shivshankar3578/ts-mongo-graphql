# Examples

```graphql
query GetRecipes {
  recipes {
    _id
    title
    author {
      email
    }
    ratings {
      value
    }
  }
}
```

```graphql
query GetRecipe {
  # fill with correct ObjectId
  recipe(recipeId: "5c97eecbf49a072a00048ac5") {
    _id
    title
    ratings {
      value
      user {
        nickname
      }
      date
    }
    author {
      _id
      nickname
      email
    }
  }
}
```

```graphql
mutation AddRecipe {
  addRecipe(recipe: { title: "New Recipe" }) {
    _id
    ratings {
      value
    }
    author {
      nickname
    }
  }
}
```
```graphql
mutation RateRecipe {
  # fill with correct ObjectId
  rate(rate: { recipeId: "5c97eecbf49a072a00048ac5", value: 4 }) {
    _id
    ratings {
      value
      user {
        email
      }
    }
  }
}
```