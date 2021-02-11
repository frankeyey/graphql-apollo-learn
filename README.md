# Building APIs With GraphQL in Node.js Application
This repo is just for learning purpose, it is a clone from [AppSignal blog](https://blog.appsignal.com/2020/06/03/building-apis-with-graphql-in-your-node-application.html). The blog guides on building a [GraphQL API](https://graphql.org/) using [Node.js](https://nodejs.org/en/) and [PostgresQL](https://www.postgresql.org/).

For more information, please refer to the original [blog post](https://blog.appsignal.com/2020/06/03/building-apis-with-graphql-in-your-node-application.html).

### Token in HTTP Header
```
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6NSwibG9naW4iOiJhcHBzaWduYWwiLCJpYXQiOjE1ODk5MTYyNTAsImV4cCI6MTU4OTkxNjQzMH0.bGDmyi3fmEaGf3FNuVBGY7ReqbK-LjD2GmhYCc8Ydts"
}
```

### Query brand
```
query($brand: String!) {
    beers(brand: $brand) [
        id
        name
        brand
        price
    ]
}
```

### Fragment
```
query getBeers($id1: Int!, $id2: Int!) {
  beer1: beer(id: $id1) {
    ...beerFields
  }
  beer2: beer(id: $id2) {
    ...beerFields
  }
}

fragment beerFields on Beer {
  id
  name
  brand
  price
}
```
### Query Variables
```
{
  "id1": 1,
  "id2": 3
}
```