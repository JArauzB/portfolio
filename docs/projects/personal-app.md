---
sidebar_label: App mobile Psonal
sidebar_position: 3
---

# App mobile Psonal

**Category:** Apps  
**Tools:** React Native, Node.js, MySQL, AWS (ECS, ECR), GitLab CI/CD, Docker, Expo  

Designed and developed a centralized cross-platform mobile application for iOS and Android focused on municipal and public services, inspired by Estonia’s digital governance model and the Dutch digital identity ecosystem (DigiD, Yivi).

---

## Project Overview

Psonal addresses the fragmentation of digital services that citizens face when interacting with government institutions, insurance providers, job platforms, and local community services. When relocating to a new city, users are often required to install and manage multiple region-specific applications, resulting in inefficiency and digital clutter.

The goal of this project was to design and implement a scalable mobile platform that centralizes essential public services into a single application. The system adapts content based on user profile attributes such as:

- Age group (Junior, Medior, Senior)
- Preferences
- Location

---

## Problem Context

Users typically rely on multiple applications for:

- Government services
- Insurance providers
- Job searching
- Healthcare access
- Supermarket discounts
- Local events and activities

This fragmentation becomes more problematic when moving to another city.

![App mobile Psonal](/img/portfolio/psonal_background.png)

Psonal centralizes these services into a single structured platform.

---

## User-Centered Design

### Core Use Cases

The system supports three primary actors:

- Junior
- Medior
- Senior

All actors share the same authentication core but receive different default options.

**Core Functionality Use Case Diagram**

![Use Case Core Functionality](/img/portfolio/psonal_usecase_core.png)

**Age-Based Option Use Case (Junior Example)**

![Use Case Junior Options](/img/portfolio/psonal_usecase_junior.jpeg)

---

## System Architecture

### High-Level System Architecture

The backend infrastructure runs on a private Debian server using Docker containers:

- MySQL database
- Node.js backend API
- Self-hosted GitLab
- GitLab Runner (CI/CD)
- IRMA/Yivi authentication container

![System Architecture](/img/portfolio/psonal_system_architecture.png)

This ensures:

- Infrastructure control
- Secure deployment
- Automated builds
- Scalable containerized services

---

## Layered Architecture

Both backend and mobile follow a layered architecture model:

1. Presentation Layer (UI)
2. Business Logic Layer
3. Persistence Layer
4. API / External Data Layer

![Layer Architecture](/img/portfolio/psonal_layer_architecture.png)

Benefits:

- Separation of concerns
- High testability
- Maintainability
- Scalability

---

## Backend Design

The backend is built using Node.js and Express, exposing REST endpoints for:

- User management
- Option retrieval
- Language configuration

### Module Dependency Structure

![Backend Module Dependency Graph](/img/portfolio/psonal_backend_modules.png)

Each route is isolated with its own controller and middleware handling:

- Rate limiting
- CORS validation
- Input validation

---

## Tree-Based Option System

The dynamic option system is implemented using a hierarchical tree structure.

- Root node contains primary categories
- Each node may contain multiple children
- New services can be added without modifying core logic

![Option Tree Structure](/img/portfolio/psonal_option_tree.png)

This design follows SOLID principles:

- Single Responsibility Principle
- Open/Closed Principle
- Liskov Substitution Principle

---

## Process Flow Example – Login

The login process demonstrates interaction between mobile layers and backend services.

![Login Sequence Diagram](/img/portfolio/psonal_login_sequence.png)

Flow summary:

1. User submits credentials in mobile app.
2. Mobile controller validates input.
3. Backend validates credentials.
4. Database query retrieves user.
5. Verification code is confirmed.
6. User gains access to personalized options.

---

## CI/CD Pipeline

The project uses GitLab CI/CD to automate testing and deployment.

**Pipeline Flow**

![GitLab CI/CD Flow](/img/portfolio/psonal_gitlab_flow.png)

Key aspects:

- Tests run on every branch push
- Minimum 80% code coverage required
- Only main branch triggers deployment
- Automatic failure notifications

**Branching Strategy**

![Branching Strategy](/img/portfolio/psonal_branching_strategy.png)

Feature branching ensures:

- Isolated development
- Clean pull requests
- Stable production releases

---

## Mobile Application Structure

Developed with React Native and Expo.

### Folder Structure

![Mobile Folder Structure](/img/portfolio/psonal_mobile_structure.png)

Main folders:

- `tabs/` – Navigation screens
- `option/` – Dynamic option views
- `components/` – Reusable UI components

Reusable components prevent duplication and improve maintainability.

---

## Database Design

The database is structured to minimize personal data exposure.

- Encrypted passwords
- No visible plaintext credentials
- Preference-based tables
- Age-based default options

![Database Schema](/img/portfolio/psonal_database_schema.png)

MySQL was chosen due to its suitability for read-heavy workflows.

---

## Security & Authentication

Current implementation includes:

- Encrypted password storage
- Email verification
- Multi-factor authentication (SMS or email)
- Request rate limiting

Future-ready integration:

- DigiD authentication
- Yivi (attribute-based privacy authentication)

---

## Testing Strategy

- Test-Driven Development (TDD)
- Jest-based backend testing
- Automated CI validation
- Code coverage target: ≥ 80%
- Postman for API documentation

Pipeline halts deployment on failed tests.

---

## Project Management Approach

Agile methodology was used:

- Weekly sprint meetings
- Scrum board
- Milestone tracking
- Risk assessment matrix

Identified risks:

- API version changes
- Data breaches
- Timeouts
- Learning curve challenges

Risk severity evaluated through probability-impact matrix and reviewed weekly.

---

## Long-Term Vision

Psonal is designed as a modular platform rather than a finished product.

Each “Option” functions as a scalable subproject. New modules can be integrated without altering the core architecture.

Potential future integrations:

- Government APIs
- Waste collection calendars
- Job platforms
- Insurance services
- Community events

The architecture ensures extensibility and long-term scalability.

---

## Conclusion

Psonal demonstrates how municipal and public services can be centralized into a secure, modular, and extensible mobile platform.

The project validates:

- Scalable architecture
- Secure authentication practices
- CI/CD automation
- Modular service integration
- Cross-platform deployment

It serves as a proof-of-concept platform capable of evolving into a fully integrated digital public service ecosystem.
