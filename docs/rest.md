
# REST – A Standard Way to Design APIs

## What is REST?
REST (Representational State Transfer) is an **architectural style** used to design **consistent, scalable, and predictable APIs** over HTTP.

> HTTP defines **how communication happens**  
> REST defines **how APIs should be structured**

REST does not replace HTTP — it **uses HTTP correctly**.

---

## Why REST Was Introduced
Before REST:
- APIs had random URL structures
- Different rules in different systems
- Hard for developers to understand and maintain

REST introduced a **uniform way** to:
- Design meaningful URLs
- Use HTTP methods properly
- Exchange data between systems

---

## Core REST Principles

### 1. Everything is a Resource
In REST, APIs deal with **resources**, not actions.

Examples of resources:
- Users
- Orders
- Products

---

### 2. Each Resource Has a Unique URL
Resources are identified using URLs.

```text
/users
/users/1
/orders/10
````

The URL represents **what resource you are accessing**, not **what action you are performing**.

***

### 3. Use HTTP Methods Properly

REST uses standard HTTP methods to define **actions** on resources.

| HTTP Method | Purpose                | Example         |
| ----------- | ---------------------- | --------------- |
| GET         | Retrieve data          | GET /users/1    |
| POST        | Create data            | POST /users     |
| PUT         | Update entire resource | PUT /users/1    |
| DELETE      | Remove resource        | DELETE /users/1 |

***

### 4. Stateless Communication

Each REST request contains **all the information** the server needs to process it.

*   Server does not store client state
*   Each request is independent
*   Improves scalability and reliability

***

## REST API Example

### Request

```http
GET /users/1 HTTP/1.1
Host: example.com
```

### Response

```json
{
  "id": 1,
  "name": "Mohit",
  "email": "mohit@example.com"
}
```

***

## Create Resource Example

### Request

```http
POST /users
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

## Advantages of REST

✅ Simple and easy to understand  
✅ Uses standard HTTP concepts  
✅ Human-readable and debuggable  
✅ Widely adopted in the industry  
✅ Supported by all platforms and languages

***

## Limitations of REST

❌ Over-fetching (extra unnecessary data)  
❌ Under-fetching (missing required data)  
❌ Multiple API calls needed for one screen

These limitations become more visible in:

*   Mobile applications
*   Frontend-heavy systems

***

## Key Takeaway

✅ REST brings **structure and discipline** to HTTP APIs  
✅ REST is easy to learn and widely used  
❌ REST is not ideal when clients need flexible data formats

➡️ These challenges led to **GraphQL**.



