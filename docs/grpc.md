
# GraphQL – Flexible and Client‑Driven APIs

## What is GraphQL?
GraphQL is a **query language for APIs** and a **runtime** that allows clients to request **exactly the data they need**.

> REST → Server decides the response  
> GraphQL → Client decides the response

GraphQL still uses **HTTP** for transport but changes **how data is fetched**.

---

## Why GraphQL Was Introduced
REST APIs started to show limitations as applications grew more complex:

- Over-fetching (getting extra unused data)
- Under-fetching (missing required data)
- Multiple API calls for a single screen

GraphQL was introduced to:
- Reduce unnecessary data transfer
- Minimize network calls
- Give more control to frontend clients

---

## Core Concepts of GraphQL

### 1. Single Endpoint
GraphQL APIs usually expose **one endpoint**.

```text
POST /graphql
````

All queries and mutations go through this endpoint.

***

### 2. Strongly Typed Schema

GraphQL APIs are defined using a **schema**.

The schema defines:

*   Types
*   Fields
*   Relationships between data

Example:

```graphql
type User {
  id: ID
  name: String
  email: String
}
```

***

### 3. Client Specifies Required Fields

Clients request **only the fields they need**.

This completely avoids over-fetching.

***

## GraphQL Query Example

### Query

```graphql
query {
  user(id: 1) {
    name
    email
  }
}
```

### Response

```json
{
  "data": {
    "user": {
      "name": "Mohit",
      "email": "mohit@example.com"
    }
  }
}
```

✅ No extra fields  
✅ Clear and predictable response

***

## Fetching Related Data in One Call

### Query

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

### Response

```json
{
  "data": {
    "user": {
      "name": "Mohit",
      "posts": [
        {
          "title": "Understanding GraphQL"
        }
      ]
    }
  }
}
```

✅ REST would need multiple APIs  
✅ GraphQL returns everything in one response

***

## Mutations (Creating or Updating Data)

### Mutation Example

```graphql
mutation {
  createUser(name: "Mohit", email: "mohit@example.com") {
    id
    name
  }
}
```

***

## Advantages of GraphQL

✅ Fetch only required data  
✅ Single endpoint  
✅ Reduced number of API calls  
✅ Excellent for frontend‑heavy applications  
✅ Strong typing improves developer experience

***

## Limitations of GraphQL

❌ More complex backend implementation  
❌ Caching is harder than REST  
❌ Not ideal for simple CRUD APIs  
❌ Requires careful authorization design

***

## When to Use GraphQL

✅ Complex UI screens  
✅ Mobile applications  
✅ Applications with many frontend clients  
✅ Rapidly changing frontend requirements

❌ Simple backend services  
❌ High‑performance internal microservices

***

## Key Takeaway

✅ GraphQL gives **more power to the client**  
✅ Solves REST’s over‑fetching and under‑fetching problems  
❌ Adds complexity compared to REST

➡️ For high‑performance service‑to‑service communication, **gRPC** is often preferred.

Say **“gRPC next”**, and we’ll complete the full comparison set cleanly 🚀
````
