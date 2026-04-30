# Order-Processing-Inventory-Integration-System
Enterprise-style order processing system using MuleSoft Anypoint Platform that integrates inventory, payment, and order services via API-led architecture.

<br>

## 🏗️ Architecture (API-Led)

You’ll follow MuleSoft’s 3-layer architecture:

1. System APIs (Data Access Layer)

These simulate backend systems:

**Inventory API**
- GET /inventory/{productId}
- PATCH /inventory/{productId} (reduce stock)
**Payment API**
  - POST /payments (mock success/failure)
**Order DB API**
  - POST /orders (store order)

<br> 

## Key Mule Components
- HTTP Listener – receive requests
- HTTP Request – call other APIs
- DataWeave – transform data
- Choice Router – business logic decisions
- Error Handler – manage failures
- Logger – debugging + monitoring
- VM Queue (optional) – async processing
