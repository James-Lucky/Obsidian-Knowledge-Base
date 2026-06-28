## 🗺️ Overview

| Aspect        | Monolithic                | Microservices                             |
| ------------- | ------------------------- | ----------------------------------------- |
| Structure     | Single deployable unit    | Collection of small, independent services |
| Codebase      | One unified codebase      | Separate codebase per service             |
| Deployment    | Deploy entire app at once | Deploy services independently             |
| Scaling       | Scale the whole app       | Scale individual services                 |
| Tech Stack    | Usually single stack      | Polyglot (each service can differ)        |
| Communication | In-process function calls | Network (HTTP/REST, gRPC, message queues) |
| Failure       | One failure can crash all | Isolated failure (ideally)                |

---

## 🧱 Monolithic Architecture

### What It Is

A single application where all components — UI, business logic, data access — are tightly coupled and deployed as **one unit**.

```
┌────────────────────────────────────┐
│           Monolithic App           │
│  ┌──────┐  ┌────────┐  ┌────────┐ │
│  │  UI  │  │Business│  │  Data  │ │
│  │Layer │→ │ Logic  │→ │ Access │ │
│  └──────┘  └────────┘  └────────┘ │
│                  ↓                 │
│           Single Database          │
└────────────────────────────────────┘
```

### Characteristics

- Single process, single deployable artifact (`.jar`, `.exe`, Docker image)
- All modules share the same memory space
- Direct function/method calls between modules — no network overhead
- One database (typically)
- Horizontal scaling = cloning the **entire** application

### ✅ Advantages

**Simplicity**

- Easy to develop initially — no distributed systems complexity
- One codebase, one repo, one CI/CD pipeline
- Debugging is straightforward — single stack trace, single log stream

**Performance**

- No network latency for inter-module calls
- Shared memory → faster data sharing between modules

**Development Speed (Early Stage)**

- Faster to build MVP
- No service boundary overhead
- Easier for small teams

**Operational Simplicity**

- One app to deploy, monitor, and manage
- No service discovery, no API gateway needed early on

### ❌ Disadvantages

**Scalability Bottleneck**

- Can't scale individual components — must scale everything
- If only the payments module needs more resources, you scale the entire app

**Deployment Risk**

- Any change requires redeploying the whole app
- One bug in one module can bring everything down

**Technology Lock-in**

- Entire app is tied to one language/framework
- Hard to adopt new tech incrementally

**Codebase Complexity Over Time**

- As the app grows, codebase becomes a "big ball of mud"
- Tight coupling makes changes risky — touching one thing breaks another

**Team Scalability**

- Multiple teams working on the same codebase = merge conflicts, coordination overhead

**Long Build/Test Cycles**

- Even a small change triggers a full build and test suite

---

## 🔬 Microservices Architecture

### What It Is

Application is decomposed into **small, loosely coupled, independently deployable services**, each responsible for a specific business capability.

```
         ┌─────────────┐
         │  API Gateway │
         └──────┬───────┘
                │
    ┌───────────┼───────────┐
    ↓           ↓           ↓
┌────────┐ ┌────────┐ ┌────────┐
│  User  │ │Product │ │ Order  │
│Service │ │Service │ │Service │
└───┬────┘ └───┬────┘ └───┬────┘
    ↓           ↓           ↓
┌────────┐ ┌────────┐ ┌────────┐
│ Users  │ │Products│ │ Orders │
│   DB   │ │   DB   │ │   DB   │
└────────┘ └────────┘ └────────┘
```

### Core Principles

- **Single Responsibility** — each service does one thing well
- **Loose Coupling** — services don't know each other's internals
- **High Cohesion** — related logic lives in the same service
- **Own Data** — each service owns its database (no shared DB)
- **Independently Deployable** — CI/CD per service

### ✅ Advantages

**Independent Scalability**

- Scale only what needs to be scaled
- e.g., Scale `OrderService` during peak sales without touching `UserService`

**Technology Flexibility (Polyglot)**

- Each service can use the best tool for its job
- `RecommendationService` in Python (ML), `PaymentService` in Go (performance), `UIService` in Node

**Fault Isolation**

- A crash in `NotificationService` doesn't kill `PaymentService`
- Requires proper circuit breakers and fallbacks

**Independent Deployments**

- Teams deploy their services without coordinating with others
- Faster release cycles

**Team Autonomy (Conway's Law)**

- Teams own their services end-to-end
- Clear ownership, clear accountability

**Easier to Understand Each Piece**

- Each service is small and focused
- New devs can onboard to one service without knowing the whole system

### ❌ Disadvantages

**Distributed Systems Complexity**

- Network calls can fail — need retries, timeouts, circuit breakers
- Latency adds up across service chains
- Partial failures are hard to handle

**Data Management Nightmare**

- No shared DB → cross-service queries are hard
- Maintaining data consistency across services requires eventual consistency, sagas, or distributed transactions

**Operational Overhead**

- Need: service discovery, API gateway, load balancers, distributed tracing, centralized logging, health checks
- Kubernetes, Istio, Prometheus, Jaeger — complex infra

**Testing Difficulty**

- Integration testing requires spinning up multiple services
- Contract testing, end-to-end testing becomes complex

**Network Overhead**

- What was a function call is now an HTTP/gRPC request
- Serialization/deserialization cost

**Debugging is Harder**

- Tracing a request across 10 services requires distributed tracing (Jaeger, Zipkin)
- Logs are spread across multiple services

---

## 🔄 Communication Patterns in Microservices

### Synchronous

- **REST (HTTP/HTTPS)** — most common, simple, stateless
- **gRPC** — binary, faster, strongly typed, uses Protocol Buffers
- **GraphQL** — flexible querying, useful for BFF (Backend for Frontend) pattern

### Asynchronous

- **Message Queues** — RabbitMQ, ActiveMQ
- **Event Streaming** — Kafka, AWS Kinesis
- **Pub/Sub** — Google Pub/Sub, Redis Pub/Sub

> **Rule of thumb**: Use async for operations that don't need immediate response (notifications, emails, analytics). Use sync for queries that need real-time data.

---

## 🗃️ Data Management Strategies

### Database per Service (Correct Approach)

Each service has its own DB — could be different types:

- `UserService` → PostgreSQL
- `CatalogService` → Elasticsearch
- `CartService` → Redis
- `AnalyticsService` → Cassandra

### Handling Cross-Service Data Needs

**API Composition**

- Query multiple services and aggregate in API Gateway or a dedicated aggregator service

**CQRS (Command Query Responsibility Segregation)**

- Separate read and write models
- Write to one service, publish event, other services update their read models

**Event Sourcing**

- Store state as a sequence of events
- Rebuild state by replaying events
- Works well with Kafka

**Saga Pattern** (for distributed transactions)

- Choreography: Services emit events and react to each other's events
- Orchestration: A central saga orchestrator tells services what to do

---

## ⚖️ When to Use What

### Use Monolithic When:

- Small team (< 10 devs)
- Early-stage startup / MVP
- Domain is not yet well-understood — premature decomposition is costly
- Simple application with low complexity
- You don't have DevOps/infra expertise

### Use Microservices When:

- Large teams that need to work independently
- Different parts of the system have drastically different scaling needs
- You need polyglot technology choices
- High availability and fault tolerance are critical
- You have mature DevOps culture and tooling (CI/CD, containers, orchestration)
- Business domains are well-understood and stable

> **Martin Fowler's rule**: Start monolith. Migrate to microservices when the monolith becomes a real problem — not before.

---

## 🔀 Migration: Monolith → Microservices

### Strangler Fig Pattern

- Incrementally replace parts of the monolith with microservices
- Route traffic to new service, keep the rest in the monolith
- Works without a big-bang rewrite

```
Step 1: Monolith handles everything
Step 2: Extract UserService, route /users to it
Step 3: Extract OrderService, route /orders to it
Step 4: Repeat until monolith is gone (or shrunk)
```

### Anti-Pattern: Distributed Monolith

- Microservices that are **tightly coupled** — deployed separately but can't function independently
- Worst of both worlds: distributed complexity + monolithic coupling
- Happens when services share a DB or one service calls another synchronously in a chain

---

## 🛠️ Key Tools & Tech

|Concern|Tools|
|---|---|
|Containerization|Docker|
|Orchestration|Kubernetes (K8s)|
|API Gateway|Kong, AWS API Gateway, NGINX|
|Service Mesh|Istio, Linkerd|
|Message Broker|Kafka, RabbitMQ|
|Distributed Tracing|Jaeger, Zipkin, OpenTelemetry|
|Centralized Logging|ELK Stack (Elasticsearch, Logstash, Kibana), Loki|
|Monitoring|Prometheus + Grafana|
|Service Discovery|Consul, Kubernetes DNS|
|Config Management|Vault, AWS Secrets Manager|

---

## 🧠 Key Concepts to Know

### 12-Factor App

Set of principles for building scalable, maintainable services:

- Config in environment variables
- Stateless processes
- Port binding
- Disposability (fast startup/shutdown) → [[12-Factor App]]

### CAP Theorem

In a distributed system, you can only guarantee 2 of 3:

- **C**onsistency — every read gets the latest write
- **A**vailability — every request gets a response
- **P**artition Tolerance — system works despite network partitions

Microservices typically trade **consistency** for **availability + partition tolerance** → eventual consistency.

### Circuit Breaker Pattern

Prevents cascading failures:

- **Closed**: requests flow normally
- **Open**: requests fail fast (service is down)
- **Half-Open**: test if service has recovered → Libraries: Hystrix (Java), `opossum` (Node.js), Resilience4j

---

## 📊 Comparison Summary

```
Complexity:      Monolith ▓▓░░░░░░░░  Microservices ▓▓▓▓▓▓▓▓▓▓
Scalability:     Monolith ▓▓▓░░░░░░░  Microservices ▓▓▓▓▓▓▓▓▓▓
Dev Speed(early):Monolith ▓▓▓▓▓▓▓▓▓▓  Microservices ▓▓▓▓░░░░░░
Dev Speed(scale):Monolith ▓▓▓░░░░░░░  Microservices ▓▓▓▓▓▓▓▓░░
Fault Isolation: Monolith ▓▓░░░░░░░░  Microservices ▓▓▓▓▓▓▓▓░░
Ops Overhead:    Monolith ▓▓░░░░░░░░  Microservices ▓▓▓▓▓▓▓▓▓░
```

---

## 🔗 Related Notes

- [[System Design Basics]]
- [[Docker & Kubernetes]]
- [[API Design - REST vs gRPC]]
- [[Database Sharding & Scaling]]
- [[Event-Driven Architecture]]
- [[CAP Theorem]]
- [[CI/CD Pipelines]]

---

_Tags: #system-design #architecture #monolith #microservices #backend #distributed-systems_