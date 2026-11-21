C Programming - Assignment 4
Student: E. YEDUKONDALU
Register Number: 192312315
Course: CSA02 - C Programming
Course Outcome: CO4
Assignment: Modelling Real-World Data with Structures and Unions

📋 Assignment Overview
This repository contains all 6 tasks for C Programming Assignment 4, covering structures, nested structures, unions, memory layout, storage classes, and a complete canteen inventory system.

Build Standard
All programs compiled with:

gcc -std=c11 -Wall -Wextra -pedantic source.c -o program
For two-file extern example:

gcc -std=c11 -Wall -Wextra -pedantic main_global.c counter.c -o task5_extern_global
📁 Repository Structure
ca/
├── Task1.pdf          # Task 1: Data Design Review (Patient structures)
├── Task2.pdf          # Task 2: Nested Structures for Parcels
├── Task3.pdf          # Task 3: Unions and Memory Layout
├── Task4.pdf          # Task 4: Structure Forensics (Pointers)
├── Task5.pdf          # Task 5: Storage Classes (4 ways)
├── Task6.pdf          # Task 6: Canteen Inventory & Billing
│

│
└── network_firewall_monitor/            # Separate Computer Networks project
📚 Task Details
Task 1: Data Design Review — Patient Structures
Topic: Diagnosing parallel-array design flaws and designing a structure-based patient record system.

Key Concepts:

Problems with parallel arrays (misalignment, sorting complexity)
Structure definitions: Date, BloodPressure, Patient
addPatient() validation pseudocode
Memory layout: sizeof(Patient), padding, alignment
Selection sort O(n²) vs parallel array swaps
Execution Evidence:

Task01 - task1_patient - PASS
630000135626 Arun 20 9876543210 120/80 19/11/2026
Task 2: Nested Structures for Parcels
Topic: Modelling parcel booking system with nested address/date structures.

Key Concepts:

Entities: Date, Address, Person, Parcel, ServiceType
Nested address/date structures inside parcel
Selection sort by weight (swap complete structures)
List by receiver city
Access path: bookings[2].receiver.address.pincode
Execution Evidence:

Task02 - task2_parcel - PASS
630000135626 1.2 kg Chennai-600077 12/10/2026
503 2.8 kg Coimbatore-641001 13/10/2026
501 4.5 kg Madurai-625001 12/10/2026
Task 3: Unions and Memory Layout
Topic: Tagged unions vs structures, memory overlay, sizeof analysis.

Key Concepts:

Structure reserves space for ALL members
Union overlays members; size = largest member + alignment
Enum tag identifies active member
Typical GCC 64-bit: union=8 bytes, struct reading=12 bytes
Never read inactive union member; check tag first
O(N) storage, O(1) access for tagged-union array
Execution Evidence:

Task03 - task3_tagged_union - PASS
sizeof union = 8, sizeof struct reading = 12
Temp 31.5 C Humidity 68 % Status OK
Task 4: Structure Forensics — Pointer-Based Updates
Topic: Pass-by-value vs pass-by-pointer, address matching proof.

Key Concepts:

Pass-by-value modifies local copy only
Pointer syntax: p->number or (*p).number (not p.number)
addInterest(struct account *a, float rate) receives address
Address pairs match between caller and function
Passing choices: by-value / pointer / const pointer
Execution Evidence:

Task04 - task4_account - PASS
main address: 0x7ffd9e57d660 function address: 0x7ffd9e57d660
main address: 0x7ffd9e57d668 function address: 0x7ffd9e57d668
main address: 0x7ffd9e57d670 function address: 0x7ffd9e57d670
Updated balances: 101 5200.00 102 12480.00 103 832.00
Task 5: Storage Classes — Same Counter Four Ways
Topic: Implementing a counter using auto, static, extern, and register.

Key Concepts:

Kind	Scope	Lifetime	Behaviour
auto	Block	Block execution	Indeterminate if not init
static local	Block	Entire program	Zero-init; retains value
extern global	External	Entire program	One definition owns storage
register	Block	Block execution	Hint only; no & allowed
Four Implementations:

Automatic local — reinitialized each call → always 1001
Static local — persists → 1001, 1002, 1003...
Global with extern — shared across files → 1001, 1002, 1003
Register loop variable — hint only, not persistent
Execution Evidence:

Task05 - task5_static_auto - PASS
static: 1001 1002 1003  auto: 1001 1001 1001

Task05 - task5_extern_global - PASS
extern/global: 1001 1002 1003

Task05 - task5_register - PASS
Token 1001 Token 1002 Token 1003
Task 6: College Canteen Inventory & Billing
Topic: Complete inventory system with tagged union for item variants.

Key Concepts:

Data model: Date, Item, PackagedInfo, CookedInfo, ComboInfo, ItemKind
Tagged union: kind must match active detail member
Sale: find by ID, validate stock, update stock + revenue
Expiry scan: convert dates to day numbers, find items expiring in 0-2 days
Daily summary: selection sort by revenue (descending)
Memory: union size = largest variant + tag + padding
Execution Evidence:

Task06 - task6_canteen - PASS
1296510135578 Sale 2 milk: accepted
Sale 3 sandwiches: accepted Sale 20 milk: rejected
Expiring: Milk in 1 day(s)
Revenue summary (highest first):
Sandwich: Rs. 150.00 (stock 2) Milk: Rs. 60.00 (stock 8) ComboMeal: Rs. 0.00 (stock 4)
📄 Generated PDFs
Each task has its own PDF with full explanation and execution evidence:

Task1.pdf — Data Design Review
Task2.pdf — Nested Structures for Parcels
Task3.pdf — Unions and Memory Layout
Task4.pdf — Structure Forensics
Task5.pdf — Storage Classes
Task6.pdf — Canteen Inventory & Billing



✅ Viva Quick Revision
Structure stores ALL members; union SHARES storage
Use -> with pointer to structure
Pass by value = copy; pass pointer = modify original
static local retains value throughout program
extern declares object defined elsewhere
sizeof may include padding; measure rather than assume
Tagged union's tag must agree with active member
CSA02 C Programming Assignment 4 — Modelling Real-World Data with Structures and Unions
