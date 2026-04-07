# GraphQL Example – Client‑Driven Data Fetching

This example demonstrates how **GraphQL** allows clients to request **exactly the data they need**, solving the over‑fetching and under‑fetching problems of REST APIs.

---

## Scenario
A client needs **only the user’s name**, not the full user object.

With REST, the server decides the response.  
With GraphQL, the **client decides the response shape**.

---

## GraphQL Endpoint
```text
POST /graphql
````

All queries and mutations are sent to a **single endpoint**.

***

## GraphQL Query (Fetch Specific Fields)

### Query

```graphql
query {
  user(id: 1) {
    name
  }
}
```

***

## GraphQL Response

```json
{
  "data": {
    "user": {
      "name": "Mohit"
    }
  }
}
```

✅ Only the requested field is returned  
✅ No extra or unused data

***

## Fetch Related Data in One Request

### Scenario

The client needs:

*   User name
*   Titles of the user’s posts

### GraphQL Query

```graphql
query {
  user(id: 1) {
    name
    posts {
      title
    }
  }
}
```

***

### GraphQL Response

```json
{
  "data": {
    "user": {
      "name": "Mohit",
      "posts": [
        {
          "title": "Learning GraphQL"
        },
        {
          "title": "REST vs GraphQL"
        }
      ]
    }
  }
}
```

✅ Single request  
✅ Nested related data  
✅ No multiple API calls

***

## Mutation Example (Create Data)

### GraphQL Mutation

```graphql
mutation {
  createUser(name: "Mohit", email: "mohit@example.com") {
    id
    name
  }
}
```

***

## Why This Is GraphQL

✅ Client controls response structure  
✅ Avoids over‑fetching  
✅ Avoids under‑fetching  
✅ One endpoint for all operations

***

## Trade‑Offs of GraphQL

❌ More complex backend  
❌ Caching is harder than REST  
❌ Overkill for simple CRUD APIs

***

## Key Takeaway

✅ GraphQL is ideal for **frontend‑heavy and complex UIs**  
✅ Reduces the number of API calls  
❌ Adds backend complexity

➡️ For **high‑performance internal service‑to‑service communication**, **gRPC** is a better fit.

