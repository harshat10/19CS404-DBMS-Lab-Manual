# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

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
<img width="842" height="612" alt="1" src="https://github.com/user-attachments/assets/3f41ab73-9c34-41fe-9841-c5a6e6e3be73" />


### Entities and Attributes

| Entity          |         Attributes (PK, FK)               | Notes    |
|-----------------|-------------------------------------------|----------|		
| Trainer         | Trainer_ID,Trainer_Name                   |          | 
| Member          |Member_ID,Member_Name,Membership_type      |          |       
| Fitness_Program	| Yoga, Zumba, Weight_Training              |          |       
| Session	        | Session_ID, Attendance                    |          |       
| Payment 	      | Payment_ID, Amount                        |          |

### Relationships and Constraints

|         Relationship       |  Cardinality | Participation | Notes |
|----------------------------|--------------|---------------|-------|
| Trainers ↔ Members         | many-to-many | book          |       |
| Members ↔ Fitness_Program  | many-to-many | enroll        |       |
| Trainers ↔ Fitness_Program | many-to-many | assigned to   |       |
| Trainers ↔ Session         | one-to-many  | conducted by  |       |
| Session ↔ Payment          | one-to-one   | generates     |        |

### Assumptions

Each member and trainer has a unique ID.

A member can enroll in more than one fitness program.

A trainer can handle multiple sessions and programs.

Each session is conducted by one trainer and records attendance.

Each session generates one payment with a fixed amount.

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
<img width="595" height="696" alt="2 (2)" src="https://github.com/user-attachments/assets/a9c36abc-f904-4e7c-98f1-81bbdeb06004" />


### Entities and Attributes

| Entity  |      Attributes (PK, FK)          | Notes |
|---------|-----------------------------------|-------|
| Member  | Member_ID,Member_Name,Phone_no    |       |
| Book    | Book_ID,Title,Author              |       |
| Loan    | Loan_ID,Loan_Date,Return_Date     |       |
| Event   | Event_ID,Event_Name,Event_Date    |       |                    
| Speaker | Speaker_ID,Speaker_Name,Expertise |       |
| Room    | Room_no, Capacity, Purpose        |       |


<img width="618" height="350" alt="image" src="https://github.com/user-attachments/assets/1cf3588e-0829-42ad-9bb6-13b967fe4983" />


### Assumptions

Each member, book, event, loan, speaker, and room has a unique ID.

A member can borrow multiple books, but a book is borrowed by one member at a time.

A loan record is created for each book borrowed, with loan and return dates.

A member can register for multiple events, and each event can have many members.

Each event is conducted in one room and can have multiple speakers.

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
<img width="597" height="612" alt="Screenshot 2026-07-26 143641" src="https://github.com/user-attachments/assets/2e558f6d-b8bb-450f-a5db-d694a2d1e6d6" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| Customer        |  Customer_ID, Customer_Name, Phone_no                  |       |
|  Orders       |  Order_ID, Starter, Main, Dessert                  |       |
| Reservation        |  Reservation_ID, Date, Time                  |       |
| Table        |  Table_ID, Location, Capacity                   |       |
| Waiters       |  Waiter_ID, Name                  |       |
| Bill        | Bill_ID, Total_Amount                   |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Customer  - Orders           |   one-to-many         |    places             |       |
|  Customer  -Reservation           |  one-to-many           |  makes               |       |
|  Reservation -  Table         |  many-to-one          |   reserves              |       |
|  Reservation - Waiters          |   many-to-one            | serves              |       |
| Reservation  - Bill           |    many-to-one           |  generates              |       |
### Assumptions

Each customer, order, reservation, table, waiter, and bill has a unique ID.

A customer can place multiple orders, but each order belongs to one customer.

A customer can make multiple reservations, and each reservation is for one table.

Each reservation is served by one waiter.

