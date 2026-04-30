# Reserve-A-Ride — System Architecture

## 1. Architecture Style

The system follows a layered architecture:

Controller Layer → Service Layer → Repository Layer → Database

---

## 2. High-Level Components

### 2.1 API Layer (Controllers)
- Handles HTTP requests
- Validates input
- Delegates business logic to services

---

### 2.2 Service Layer
- Contains core business logic
- Handles booking rules, capacity checks, and payment state transitions
- Acts as system brain

---

### 2.3 Repository Layer
- Interfaces with MySQL database
- Handles CRUD operations

---

### 2.4 Database Layer
- Stores users, routes, bookings, payments, and trip data

---

## 3. Core Domain Flow

1. Driver creates route and schedule
2. Passenger books a seat
3. System checks capacity threshold (60%)
4. If threshold met → route activated
5. Trip instance is created
6. Payment is held in escrow
7. Trip execution occurs
8. Payment is released or refunded

---

## 4. Key System Principle

The system is **state-driven**, not request-driven.

Each booking, trip, and payment transitions through defined states to ensure consistency and prevent invalid operations.

---

## 5. Future Extensions

- Mobile application layer
- Real-time tracking system
- Route optimization algorithms
- Payment gateway integration