# Reserve-A-Ride — Requirements Specification

## 1. Functional Requirements

### 1.1 User Management
- The system shall allow users to register as passengers or drivers
- The system shall support authentication and role-based access control

---

### 1.2 Driver Management
- The system shall allow drivers to register vehicles
- The system shall allow drivers to create fixed commuter routes
- The system shall allow drivers to define schedules for routes

---

### 1.3 Route Management
- The system shall allow creation of routes with origin and destination
- The system shall associate routes with drivers and vehicles
- The system shall support recurring route schedules

---

### 1.4 Booking System
- The system shall allow passengers to reserve seats on routes
- The system shall enforce vehicle capacity constraints
- The system shall track booking status (reserved, confirmed, cancelled)

---

### 1.5 Capacity Rules
- The system shall only activate a route if a minimum threshold (e.g. 60%) of seats are booked
- The system shall cancel or reschedule underbooked routes

---

### 1.6 Payment Handling
- The system shall simulate escrow-based payment storage
- The system shall release funds upon trip completion
- The system shall refund passengers if trips are cancelled

---

### 1.7 Trip Execution
- The system shall generate trip instances based on active schedules
- The system shall track trip lifecycle (planned, ongoing, completed, cancelled)

---

## 2. Non-Functional Requirements

### 2.1 Reliability
- The system shall ensure consistency of booking and payment states

### 2.2 Scalability
- The system shall support multiple routes and concurrent bookings

### 2.3 Security
- The system shall protect user credentials using encryption
- The system shall restrict access based on user roles

### 2.4 Data Integrity
- The system shall ensure no overbooking of seats occurs
- The system shall maintain transactional consistency in bookings and payments

---

## 3. Constraints

- System will be implemented using Java and Spring Boot
- MySQL will be used for persistence
- Payment integration will be simulated in MVP stage
- System will follow RESTful architecture

---

## 4. Assumptions

- Users have access to mobile or web interfaces for booking
- Drivers operate on predefined daily routes
- Commuter demand exists on repeat routes