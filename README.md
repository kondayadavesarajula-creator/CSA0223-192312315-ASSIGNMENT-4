# CSA02 – C Programming Assignment 4

## Modelling Real-World Data with Structures and Unions

### Student Information

| Field | Details |
|---|---|
| **Student Name** | E. YEDUKONDALU |
| **Register Number** | 192312315 |
| **Course** | CSA02 – C Programming |
| **Course Outcome** | CO4 |
| **Assignment** | Assignment 4 |
| **Topic** | Modelling Real-World Data with Structures and Unions |
| **Programming Language** | C |
| **Compiler** | GCC 14.2.0 |
| **Standard** | C11 |

---

## 📋 Assignment Overview

This repository contains all **6 tasks** completed as part of C Programming Assignment 4 (CO4).

The assignment focuses on modelling real-world data using C structures and unions, understanding memory allocation, implementing pointer-based operations, exploring storage classes, and developing a practical canteen inventory and billing system.

### Topics Covered

- Structures and nested structures
- Unions and memory layout
- Structure pointers and pointer-based updates
- Pass-by-value and pass-by-reference using pointers
- Storage classes (`auto`, `static`, `extern`, `register`)
- Tagged unions and memory management
- Searching, sorting, and data validation
- Real-world inventory management and billing

---

## 🛠️ Build Standard

All C programs are compiled using GCC with the C11 standard and warning flags.

**Standard compilation command:**

```bash
gcc -std=c11 -Wall -Wextra -pedantic source.c -o program
```

**Task 5 – Extern Global Variable (Multiple Files):**

```bash
gcc -std=c11 -Wall -Wextra -pedantic main_global.c counter.c -o task5_extern_global
```

**Execution:**

```bash
./program
```

---

## 📁 Repository Structure

```text
CSA02-192312315-Assignment4/
│
├── Task01/
│   ├── Task1.pdf
│   └── [Source files]
│
├── Task02/
│   ├── Task2.pdf
│   └── [Source files]
│
├── Task03/
│   ├── Task3.pdf
│   └── [Source files]
│
├── Task04/
│   ├── Task4.pdf
│   └── [Source files]
│
├── Task05/
│   ├── Task5.pdf
│   └── [Source files]
│
├── Task06/
│   ├── Task6.pdf
│   └── [Source files]
│
└── README.md
```

*Note: Each task folder contains its corresponding C source files and documentation PDF.*

---

## 📚 Task Details

### Task 1: Data Design Review – Patient Structures

**Objective:** Identify the limitations of parallel arrays and design an efficient patient record management system using structures.

**Key Concepts:**
- Problems with parallel arrays, including data misalignment and sorting complexity.
- Defining structures for `Date`, `BloodPressure`, and `Patient`.
- Implementing patient record insertion using `addPatient()`.
- Understanding structure size using `sizeof()`.
- Structure padding and memory alignment.
- Selection sort with O(n²) time complexity.
- Swapping complete structure records instead of individual array elements.

**Execution Evidence:**

```text
Task01 - task1_patient - PASS

630000135626 Arun 20 9876543210 120/80 19/11/2026
```

---

### Task 2: Nested Structures for Parcels

**Objective:** Develop a parcel booking system using nested structures to represent sender, receiver, address, and booking date information.

**Key Concepts:**
- Defining `Date`, `Address`, `Person`, `Parcel`, and `ServiceType`.
- Implementing nested structures for sender and receiver details.
- Sorting parcels by weight using selection sort.
- Swapping complete structure variables.
- Displaying parcels based on receiver city.
- Accessing nested members using the dot operator.

**Example Access Path:**

```c
bookings[2].receiver.address.pincode
```

**Execution Evidence:**

```text
Task02 - task2_parcel - PASS

630000135626
1.2 kg Chennai-600077 12/10/2026 503
2.8 kg Coimbatore-641001 13/10/2026 501
4.5 kg Madurai-625001 12/10/2026
```

---

### Task 3: Unions and Memory Layout

**Objective:** Understand the differences between structures and unions and analyse their memory allocation.

**Key Concepts:**
- Structures allocate memory for all members.
- Unions share the same memory location among their members.
- Union size depends on its largest member and alignment requirements.
- Using enumerations as tags to identify active union members.
- Understanding memory overlay and `sizeof()` calculations.
- Avoiding access to inactive union members.
- Efficient memory usage through tagged unions.

**Execution Evidence:**

```text
Task03 - task3_tagged_union - PASS

sizeof union = 8
sizeof struct reading = 12

Temp 31.5 C
Humidity 68 %
Status OK
```

---

### Task 4: Structure Forensics – Pointer-Based Updates

**Objective:** Demonstrate the difference between passing structures by value and passing structure pointers to functions.

**Key Concepts:**
- Pass-by-value and its effect on local copies.
- Passing structure addresses to functions.
- Accessing structure members using the arrow (`->`) operator.
- Using pointer-based functions to modify original records.
- Understanding address matching between calling and called functions.
- Choosing between normal pointers and constant pointers.

**Example Function:**

```c
void addInterest(struct account *a, float rate);
```

**Execution Evidence:**

```text
Task04 - task4_account - PASS

main address: 0x7ffd9e57d660
function address: 0x7ffd9e57d660

main address: 0x7ffd9e57d668
function address: 0x7ffd9e57d668

main address: 0x7ffd9e57d670
function address: 0x7ffd9e57d670

Updated balances:
101 5200.00
102 12480.00
103 832.00
```

*Note: Memory addresses may differ between executions.*

---

### Task 5: Storage Classes – Implementing a Counter Four Ways

**Objective:** Explore the four C storage classes and understand their scope, lifetime, and behaviour through counter implementations.

**Key Concepts:**

| Storage Class | Scope | Lifetime | Behaviour |
|---|---|---|---|
| `auto` | Block | Block execution | Automatic local variable |
| `static` | Block (local static) | Entire program | Retains its value between function calls |
| `extern` | File/program scope | Entire program | Refers to a global variable defined elsewhere |
| `register` | Block | Block execution | Suggests register storage to the compiler |

**Four Implementations:**

1. **Automatic Variable (`auto`):** Reinitialised on each function call.
2. **Static Variable (`static`):** Retains its previous value across function calls.
3. **External Variable (`extern`):** Shares a global counter across multiple source files.
4. **Register Variable (`register`):** Demonstrates the register storage-class declaration.

**Execution Evidence:**

```text
Task05 - task5_static_auto - PASS

static: 1001 1002 1003
auto:   1001 1001 1001
```

```text
Task05 - task5_extern_global - PASS

extern/global: 1001 1002 1003
```

```text
Task05 - task5_register - PASS

Token 1001
Token 1002
Token 1003
```

---

### Task 6: College Canteen Inventory and Billing System

**Objective:** Develop a canteen inventory and billing application using structures, tagged unions, searching, sorting, and stock management.

**Key Concepts:**
- Designing structures for `Date`, `Item`, `PackagedInfo`, `CookedInfo`, and `ComboInfo`.
- Using an enumeration (`ItemKind`) to identify item types.
- Implementing tagged unions for different item categories.
- Searching inventory items using item IDs.
- Validating available stock before processing sales.
- Updating inventory quantities and revenue after successful sales.
- Identifying items that expire within 0–2 days.
- Converting dates into day numbers for expiry calculations.
- Sorting daily revenue summaries in descending order.
- Understanding union memory allocation and structure padding.

**Execution Evidence:**

```text
Task06 - task6_canteen - PASS

1296510135578

Sale 2 milk: accepted
Sale 3 sandwiches: accepted
Sale 20 milk: rejected

Expiring: Milk in 1 day(s)

Revenue summary (highest first):

Sandwich: Rs. 150.00 (stock 2)
Milk: Rs. 60.00 (stock 8)
ComboMeal: Rs. 0.00 (stock 4)
```

---

## 📄 Assignment Documentation

Individual PDF documentation is provided for all six tasks.

| PDF File | Description |
|---|---|
| `Task1.pdf` | Data Design Review – Patient Structures |
| `Task2.pdf` | Nested Structures for Parcels |
| `Task3.pdf` | Unions and Memory Layout |
| `Task4.pdf` | Structure Forensics – Pointer-Based Updates |
| `Task5.pdf` | Storage Classes – Four Implementations |
| `Task6.pdf` | College Canteen Inventory and Billing System |

Each document contains the corresponding task explanation and execution evidence.

---

## ✅ Viva – Quick Revision

| Concept | Important Point |
|---|---|
| Structure | Stores all members independently. |
| Union | Shares memory among all members. |
| Nested Structure | A structure defined as a member of another structure. |
| Structure Pointer | Uses `->` to access members. |
| Pass-by-Value | Passes a copy of the structure. |
| Pointer-Based Passing | Allows modification of the original structure. |
| `static` | Retains its value throughout program execution. |
| `extern` | Declares a variable defined in another source file or elsewhere. |
| `register` | Suggests register storage to the compiler. |
| `sizeof()` | Returns the size of a data type or object in bytes. |
| Padding | Extra bytes inserted to satisfy memory alignment. |
| Tagged Union | Uses a tag to identify the active union member. |
| Selection Sort | Sorting algorithm with O(n²) time complexity. |

---

## 🎯 Learning Outcomes

After completing this assignment, the following skills were practised:

1. Designing structured data models for real-world applications.
2. Implementing nested structures and unions in C.
3. Understanding memory allocation, alignment, and padding.
4. Using structure pointers for efficient data modification.
5. Applying different storage classes in practical programs.
6. Developing an inventory and billing system using C programming concepts.
7. Implementing searching, sorting, validation, and data management operations.

---

## 🏁 Conclusion

C Programming Assignment 4 demonstrates the practical application of structures, nested structures, unions, pointers, and storage classes in solving real-world data modelling problems.

All six tasks were implemented, compiled, and tested using GCC with the C11 standard.

**Course:** CSA02 – C Programming  
**Course Outcome:** CO4  
**Assignment:** 4 – Modelling Real-World Data with Structures and Unions

---

**Submitted by:** E. YEDUKONDALU  
**Register Number:** 192312315
