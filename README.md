# Chairfly

**Aviation training software built to support consistent practice and continued pilot proficiency.**

Chairfly is a web and iOS aviation training platform designed to give pilots and aviation organizations a structured way to practice procedures and reinforce knowledge outside the aircraft.

I founded Chairfly in 2026 and have developed the platform across the stack—from product design and database architecture to backend services, web development, native iOS development, deployment, and production support.

> **This repository is a technical showcase of the project. The production source code and implementation details are private.**

---

## Product Overview

Chairfly explores how software can make recurrent aviation practice more accessible, structured, and personalized.

The platform supports individual pilots as well as aviation organizations, requiring the underlying system to handle both personal content and shared organizational resources while maintaining appropriate ownership and access boundaries.

### Engineering at a Glance

* **Web + native iOS** applications
* **TypeScript / React** web client
* **Swift / SwiftUI** iOS client
* **Node.js** backend
* **PostgreSQL** relational data layer
* **70+** multi-tenant API routes
* **25+** database tables
* **3** database views
* **5** organization types
* Role-based access and resource ownership constraints
* Transactional updates and relational-integrity enforcement
* **25+ pilot users** supported during development

---

## System Architecture

At a high level, Chairfly uses client applications backed by a shared application and data layer:

```text
        ┌─────────────────────┐
        │      Web Client     │
        │ TypeScript / React  │
        └──────────┬──────────┘
                   │
                   │
                   │
        ┌──────────┴──────────┐
        │                     │
        │    Application API  │
        │       Node.js       │
        │                     │
        │    70+ API Routes   │
        │                     │
        └──────────┬──────────┘
                   │
                   │
          ┌────────▼────────┐
          │   PostgreSQL    │
          │                 │
          │  25+ Tables     │
          │    3 Views      │
          └─────────────────┘

        ┌─────────────────────┐
        │     iOS Client      │
        │   Swift / SwiftUI   │
        └─────────────────────┘
```

*Diagram is intentionally conceptual; production infrastructure and implementation details are not included in this repository.*

---

## Engineering Highlights

### Multi-Tenant Architecture

Chairfly supports multiple types of organizations alongside individual users.

This introduces engineering requirements beyond basic CRUD functionality: resources can exist within different organizational contexts, users can hold different roles, and operations must respect both membership permissions and resource ownership.

The backend therefore incorporates:

* Role-based access control
* Resource ownership constraints
* Organization-scoped operations
* Relational integrity
* Transactional updates

These boundaries are enforced at the application and data layers rather than relying solely on client-side behavior.

---

### Relational Data Modeling

The production PostgreSQL data model has grown to more than **25 tables and 3 views**.

The schema supports relationships between users, organizations, memberships, training content, and application state while maintaining ownership and relational constraints.

As the product expanded, database design became an important part of ensuring that new features could coexist without weakening existing authorization or data-integrity guarantees.

---

### Backend API

Chairfly's backend has grown to more than **70 API routes** supporting the web and mobile product.

Backend engineering has included work around:

* Authentication and authorization boundaries
* Resource ownership
* Input validation
* Multi-tenant operations
* Transactional state changes
* Relational data access
* Error handling
* Client/server state synchronization

The production route structure and authorization implementation remain private.

---

## Production Engineering

Chairfly has been used by **25+ pilots**, turning development from a purely local engineering exercise into an ongoing production-software problem.

Real usage has required debugging issues that emerge across client, server, and data boundaries, incorporating user feedback, and maintaining existing behavior while the underlying product continues to evolve.

This has made production reliability and maintainability important engineering considerations alongside feature development.

---

## Cross-Platform Development

Chairfly spans both web and native mobile environments.

### Web

```text
TypeScript
React
Node.js
PostgreSQL
```

### iOS

```text
Swift
SwiftUI
```

Supporting multiple clients against shared application data introduces additional considerations around state consistency, API contracts, permissions, and behavior across platforms.

---

## Engineering Philosophy

Aviation software operates in a domain where users are accustomed to procedures, clear responsibilities, and predictable behavior.

Chairfly has therefore been developed with an emphasis on:

**Clear system boundaries.**
Ownership and authorization rules should be understandable and consistently enforced.

**Data integrity.**
Operations spanning related resources should preserve the invariants of the underlying system.

**Production feedback.**
Real user behavior frequently exposes assumptions that are difficult to discover during isolated development.

**Maintainability.**
As the application grows, new functionality should strengthen rather than bypass existing abstractions and permission boundaries.

---

## Technology

| Area           | Technologies         |
| -------------- | -------------------- |
| Web            | TypeScript, React    |
| Mobile         | Swift, SwiftUI       |
| Backend        | Node.js              |
| Database       | PostgreSQL           |
| Infrastructure | Cloud infrastructure |
| Development    | Git, Docker          |

---

## Repository Purpose

This repository exists to document selected product and engineering work behind Chairfly without publishing the production application.

It contains:

```text
chairfly-showcase/
│
├── README.md
```

It intentionally does **not** contain:

* Production source code
* Database schemas or migrations
* API specifications
* Authentication or authorization implementation
* Infrastructure configuration
* Credentials or environment configuration
* Production data
* Private user or organization information
* Unreleased product plans
* Non-public information regarding users, stakeholders, collaborators, or prospective partners

---

## About

Chairfly was founded and developed by **Christopher S. Powell**, a software engineer, commercial pilot, instrument-rated pilot, and advanced ground instructor.

The project combines software engineering with direct aviation-domain experience and an interest in building better tools for pilot training and continued proficiency.

**Built by a pilot, for pilots.**
