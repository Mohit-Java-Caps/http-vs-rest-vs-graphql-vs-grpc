
# REST API Example – Resource‑Based Design

This example demonstrates how **REST APIs** use **resources**, **HTTP methods**, and **clear URL structures** to build well‑designed APIs.

---

## Scenario
A client wants to **fetch details of a user** with ID `1` from the server.

REST focuses on:
- Clear resource naming
- Proper use of HTTP methods
- Stateless communication

---

## REST Request
```http
GET /users/1 HTTP/1.1
Host: example.com
````

***

## REST Response

```json
{
  "id": 1,
  "name": "Mohit",
  "email": "mohit@example.com"
}
```

***

## Create Resource Example

### REST Request

```http
POST /users HTTP/1.1
Content-Type: application/json
```

Request Body:

```json
{
  "name": "Mohit",
  "email": "mohit@example.com"
}
```

***

## Update Resource Example

### REST Request

```http
PUT /users/1 HTTP/1.1
Content-Type: application/json
```

Request Body:

```json
{
  "name": "Mohit Kumar",
  "email": "mohit.kumar@example.com"
}
```

***

## Delete Resource Example

### REST Request

```http
DELETE /users/1 HTTP/1.1
Host: example.com
```

***

## Why This Is REST

✅ Uses **noun‑based URLs** (`/users/1`)  
✅ Uses **HTTP verbs** to define actions  
✅ Each request is **stateless**  
✅ Easy to understand and debug

***

## Limitation of REST

❌ Client always receives **all fields**, even if it needs only one  
❌ Multiple API calls may be required for complex UI screens

➡️ These limitations led to **GraphQL**, which allows clients to fetch exactly what they need.
