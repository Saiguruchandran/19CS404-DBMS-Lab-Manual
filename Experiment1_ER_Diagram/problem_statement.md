# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="798" height="492" alt="image" src="https://github.com/user-attachments/assets/8d458f88-130a-4d22-9a54-217aaa96d981" />


### Entities and Attributes

Member (MemberID, Name, MembershipType, StartDate)
 Program (ProgramID, ProgramName, Description)
 Trainer (TrainerID, Name, Specialization)
 PersonalSession (SessionID, Date, Time, MemberID (FK), TrainerID (FK))
 Attendance (AttendanceID, SessionID (FK), MemberID (FK), Status)
 Payment (PaymentID, MemberID (FK), Amount, PaymentDate,
PaymentType)
### Relationships and Constraints

Member ↔ Program → M:N
 Trainer ↔ Program → M:N
 Member ↔ PersonalSession → 1:N
 PersonalSession ↔ Attendance ↔ Member → M:N
 Member ↔ Payment → 1:N
### Assumptions
-Programs and trainers can exist without members.
-Attendance is recorded per session per member.
-Payments are linked to members (membership/session)
---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="776" height="518" alt="image" src="https://github.com/user-attachments/assets/484d627f-17ee-44ca-b7d6-2bb79c0e97d7" />


### Entities and Attributes
Member, Book, Loan, Event, Speaker, EventRegistration, Room,
Fine.
Attributes: Each entity has a PK (e.g., MemberID, BookID, EventID). Key
details like Name, Title, Author, Category, Amount are included.

### Relationships and Constraints
 Member–Loan–Book → M:N (resolved by Loan).
o Member–EventRegistration–Event → M:N.
o Event–Speaker → M:N.
o Event–Room → 1:N.
o Loan–Fine → 1:1 (if overdue).
### Assumptions
- A book can be borrowed by one member at a time.-
- Rooms are used for both study and events.
- Fines apply only for late returns.
- A member must exist to borrow books or join events.
- Each event has at least one room and one speaker
 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="859" height="486" alt="image" src="https://github.com/user-attachments/assets/6d022670-3e7b-48a0-ad8f-3929fdcf4479" />


### Entities and Attributes

o Customer: Stores customer details (CustomerID, Name, Phone).
o Reservation: Tracks reservations with date, time, number of guests,
and linked customer.
o Order: Represents food orders linked to reservations.
o Dishes: Stores dish details with category (starter, main, dessert).
o Bills: Generated for each reservation, includes food and service
charges.
o Waiter: Assigned to reservations for service.


### Relationships and Constraints

1. Customer – Reservation (1:M):
A customer can make multiple reservations, but each reservation belongs to
one customer.
2. Reservation – Order (1:M):
A reservation can have multiple orders; each order belongs to one
reservation.
3. Order – Dishes (M:N):
An order can include multiple dishes, and a dish can appear in many orders
(resolved via junction table if needed).
4. Reservation – Bills (1:1):
Each reservation generates exactly one bill.
5. Reservation – Waiter (1:N):
A waiter can serve many reservations, but each reservation is assigned to one
waiter.

### Assumptions
 A walk-in customer is treated the same as a reserved customer, with an
immediate reservation created in the system.
 Each reservation generates one consolidated bill, including both food and
service charges.
 Waiters are linked to reservations, not individual orders.
 Dishes belong to predefined categories (starter, main course, dessert).
 M:N relationship between orders and dishes may be implemented using a
separate OrderDetails table in physical design.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
