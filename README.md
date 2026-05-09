**Integration Practice Project**

# Order-Processing-Inventory-Integration-System

Enterprise-grade order processing system using MuleSoft Anypoint Platform with API-led architecture integrating inventory, payment, and order management services.

<br>

## Overview

This project implements MuleSoft's **3-layer API-led architecture**:

1. **System APIs** – Direct data access to backend systems (orders, inventory, payments)
2. **Process APIs** – Business logic orchestration and workflows
3. **Experience APIs** – Customer-facing interfaces and data transformation

RDBS: **PostgreSQL (Supabase)**

Testing: **Postman** 

The core flow: **receive order → validate → coordinate with backend systems → handle errors → return response.**

<br>

### Fig.1 - Example of UI (Eperience API)

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/e75d7240-ba17-4899-87c5-372fd6581760" />


---

## User Flow (Customer Perspective)

Customers interact with the system through a simple API where they can browse available inventory, place orders, view specific orders, and make updates if needed. Behind the scenes, the system handles inventory validation, payment processing, and order management, ensuring each request is processed reliably and returns a clear, structured response.


---

## Project Structure

```
Order-Processing-Inventory-Integration-System/
├── experience-api/              # Customer-facing APIs
├── process-api/                 # Business logic & orchestration
├── services/
│   ├── system-api-orders/       # Order data access layer
│   ├── system-api-inventory/    # Inventory data access layer
│   └── system-api-payment/      # Payment processing layer
├── pom.xml                       # Root Maven configuration
└── README.md
```

---

## Module Descriptions

### System APIs (Data Access Layer)

These modules simulate and manage backend system integrations:

- **system-api-orders** – Order database operations
  - `POST /orders` – Create order
  - `GET /orders/{orderId}` – Retrieve order

- **system-api-inventory** – Inventory management
  - `GET /inventory/{productId}` – Check stock
  - `PATCH /inventory/{productId}` – Update stock

- **system-api-payment** – Payment processing
  - `POST /payments` – Process payment (mock success/failure)

### Process API

Orchestrates business logic across system APIs, handling validation, error management, and workflow coordination.

### Experience API

Exposes customer-facing endpoints with data transformation via DataWeave and response formatting.

---

## Key Mule Components

- **HTTP Listener** – Receive incoming requests
- **HTTP Request** – Call downstream APIs
- **DataWeave** – Data transformation and mapping
- **Choice Router** – Conditional business logic
- **Error Handler** – Exception management
- **Logger** – Debugging and monitoring
- **VM Queue** – Async message processing (optional)

---

## Building & Running

### Prerequisites
- MuleSoft Anypoint Studio or Visual Studio Code
- Java 8+
- Maven 3.6+
- Supabase
- Postman
- Command Prompt/Terminal (for directory management) 

### Build
```bash
mvn clean install
```

### Run Individual Modules
```bash
# From module directory
mvn clean package mule:deploy
```

---

<br>

### DISCLAIMER 

_Please note, that the data and assets used in this project are for demonstration purposes only and do not represent real or accurate Fisher & Paykel products. All asset-related information within this project is fictional and has been created solely for demonstration. This project is a personal skills and capability showcase intended to illustrate my experience with MuleSoft Software._

<br>

## License

See LICENSE file for details.
