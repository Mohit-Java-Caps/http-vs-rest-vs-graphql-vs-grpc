

# HTTP – The Foundation of Web Communication

## What is HTTP?
HTTP (HyperText Transfer Protocol) is a **communication protocol** that defines **how data is transferred between a client and a server** over the internet.

Think of HTTP as:
> Rules for conversation between two systems.

It does NOT define:
- How APIs should look
- How URLs should be structured
- What data should be returned

It only defines **how messages are sent and received**.

---

## Why HTTP Exists
Before HTTP:
- No standard way for systems to communicate
- Custom protocols everywhere

HTTP standardized:
- Request–response communication
- Platform‑independent data exchange
- Stateless interactions

---

## Core HTTP Concepts

### 1. HTTP Methods
- GET → Read data
- POST → Create data
- PUT → Update data
- DELETE → Delete data

### 2. HTTP Status Codes
- 200 → OK
- 400 → Bad Request
- 404 → Not Found
- 500 → Server Error

---

## Simple Example

### Request
```http
GET /users/1 HTTP/1.1
Host: example.com

**### Response**
{
  "id": 1,
  "name": "Mohit"
}

**## Key Takeaway**
✅ HTTP is mandatory
❌ HTTP alone is not enough to design APIs
This led to REST.
