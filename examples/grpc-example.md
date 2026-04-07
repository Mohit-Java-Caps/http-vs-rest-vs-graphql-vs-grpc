# gRPC Example – High‑Performance Service‑to‑Service Communication

This example demonstrates how **gRPC** is used for **fast, efficient communication between backend services**, especially in microservice architectures.

Unlike REST and GraphQL, gRPC focuses on **machine‑to‑machine communication**, not human‑readable APIs.

---

## Scenario
A **User Service** needs to fetch user details from another internal service.

Key characteristics:
- No URLs
- No HTTP verbs like GET or POST
- Communication happens through **method calls**

---

## Protocol Buffers Definition

The service contract is defined using **Protocol Buffers (.proto)**.  
This contract is shared between the client and server.

### `user.proto`
```proto
syntax = "proto3";

service UserService {
  rpc GetUser (UserRequest) returns (UserResponse);
}

message UserRequest {
  int32 id = 1;
}

message UserResponse {
  int32 id = 1;
  string name = 2;
  string email = 3;
}
````

***

## gRPC Client Call

Instead of calling a URL, the client calls a **remote method**:

```text
GetUser(id = 1)
```

From the developer’s perspective, this feels like calling a local function.

***

## gRPC Response

*   The response is sent as **binary Protocol Buffer data**
*   It is automatically converted into objects by generated code
*   Developers do not manually parse JSON or XML

Example (conceptual object received by client):

```text
UserResponse {
  id: 1,
  name: "Mohit",
  email: "mohit@example.com"
}
```

***

## Streaming Support in gRPC

gRPC supports advanced communication patterns:

*   Unary (one request → one response)
*   Server streaming
*   Client streaming
*   Bi‑directional streaming

This makes gRPC well‑suited for:

*   Real‑time systems
*   Event‑driven architectures
*   Continuous data transfer

***

## Why This Is gRPC

✅ Uses method calls instead of URLs  
✅ Strongly typed contracts via `.proto`  
✅ Binary, compact payloads  
✅ Extremely fast and efficient

***

## Trade‑Offs of gRPC

❌ Not human‑readable  
❌ Hard to test without generated clients  
❌ Not easily usable from browsers

***

## When gRPC Is the Right Choice

✅ Internal microservice communication  
✅ High‑throughput systems  
✅ Low‑latency requirements  
✅ Backend‑to‑backend calls

❌ Public APIs  
❌ Simple CRUD applications  
❌ Browser‑based clients

***

## Key Takeaway

✅ gRPC provides **maximum performance and efficiency**  
✅ Ideal for **internal service‑to‑service communication**  
❌ Not designed for user‑facing APIs

➡️ In modern architectures, teams often use **REST or GraphQL externally** and **gRPC internally**.
