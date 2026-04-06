

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
- Design URLs
- Use HTTP methods
- Exchange data between systems

---

## Core REST Principles

### 1. Everything is a Resource
In REST, APIs deal with **resources**, not actions.

Examples:
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
