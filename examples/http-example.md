
# HTTP Example – Basic Client–Server Communication

This example demonstrates **plain HTTP communication** between a client and a server, without applying REST rules or API design principles.

---

## Scenario
A client wants to fetch user information from a server using HTTP.

At this level:
- HTTP only defines **how data is sent**
- It does **not** enforce URL structure
- It does **not** define resource naming

---

## HTTP Request
```http
GET /getUser?id=1 HTTP/1.1
Host: example.com
````

***

## HTTP Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "name": "Mohit"
}
```

***

## What This Shows

*   HTTP follows a **request–response** model
*   The URL can be anything (no standard naming rule)
*   Query parameters and paths are freely designed

***

## Observations

✅ HTTP successfully transfers data  
✅ Platform‑independent communication

❌ No standard API structure  
❌ No rules for naming endpoints  
❌ Hard to maintain at scale

***

## Key Takeaway

✅ HTTP defines **how communication happens**  
❌ HTTP does **not define how APIs should be designed**

➡️ This limitation led to **REST**, which introduced structure and conventions.
