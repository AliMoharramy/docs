---
sidebar_label: "chapter 1 - part 1"
sidebar_position: 1
---

# Chapter 1-1

A **database-management system (DBMS)** is a collection of interrelated data and a set of programs to access those data.  
The primary goal of a DBMS is to provide a way to store and retrieve database information that is both **convenient and efficient**.

## Purpose of Database Systems

### Data Redundancy and Inconsistency

Since different programmers create the files and application programs over a long period, the various files are likely to have different structures, and the programs may be written in several programming languages. Moreover, the same information may be duplicated in several places (files).

For example, if a student has a double major (say, music and mathematics), their address and telephone number may appear in multiple department records. This redundancy leads to:

- Higher storage and access costs.
- Data inconsistency (e.g., a changed address is updated in the Music department but not elsewhere).

#### Solution: Use a Centralized Database System

To avoid data redundancy and inconsistency, organizations use **Database Management Systems (DBMS)**. A DBMS centralizes data storage and provides controlled access to avoid duplication and inconsistency.

##### How DBMS Solves These Issues:

1. **Eliminates Redundancy:** Data is stored in one place and referenced when needed.
2. **Ensures Data Consistency:** Updates occur once in the centralized database and reflect everywhere.
3. **Improves Data Integrity:** Data is accurate and reliable across all departments.
4. **Reduces Storage Costs:** Instead of multiple copies, a single version of the data is maintained.

### Difficulty in Accessing Data

Traditional **file-processing systems** make data retrieval difficult. If a university clerk needs a specific student list (e.g., by postal code), no pre-existing program may be available. They must either:

- Filter data manually.
- Request a new program (time-consuming).

Each new query requires additional programming, making the system inefficient. A **DBMS** provides a **more responsive and flexible** data retrieval system.

### Integrity Problems

The **data values stored** in the database must satisfy certain consistency constraints. If constraints are not properly enforced, invalid or inconsistent data may exist in the system.

#### Types of Integrity Problems in Databases

1. **Entity Integrity Violation:** Every table (relation) in a database should have a Primary Key, which uniquely identifies each record. If a primary key is missing or duplicated, the table loses its integrity.

2. **Referential Integrity Violation:** A foreign key in one table should always reference a valid primary key in another table. If a referenced key is missing or deleted improperly, referential integrity is broken.

3. **Domain Integrity Violation:** Each column in a database should contain values within a specific range and data type. If invalid values are inserted, domain integrity is violated.

4. **Data Redundancy Leading to Inconsistency:** Storing the same data in multiple places can cause conflicting updates, leading to inconsistencies. If data is changed in one place but not updated elsewhere, different records may show different values for the same entity.

### Atomicity Problems

#### **What is Atomicity?**

**Atomicity** is one of the four properties of database transactions, known as **ACID** (Atomicity, Consistency, Isolation, Durability). It ensures that **a transaction is either fully completed or not executed at all**. If a failure occurs in the middle of a transaction, **no partial changes should be applied to the database**.

A computer system, like any other device, is subject to **failure**. In many applications, it is crucial that if a failure occurs, the data be **restored** to the **consistent state** that existed prior to the failure.

#### Atomicity Problems: Causes

1. **System Crashes:** A power outage or hardware failure can interrupt a transaction before completion. If a partially executed transaction is not rolled back, the database may enter an inconsistent state.

2. **Software Errors:** Bugs in the application or database system might cause transactions to stop before completing.

3. **Improper Handling of Transactions:** If developers manually execute multiple SQL statements without using transactions, partial updates can occur.

### Concurrent-Access Anomalies

When multiple users update data simultaneously, **inconsistencies** may occur. For example:

- If two clerks debit an account at the same time, the final balance might be incorrect.
- If two students register for a course at the same time, the count may not update correctly.

To prevent these issues, **concurrency control** methods like **locking** and **transactions** should be used in database systems.

#### Common Concurrent-Access Anomalies

1. **Lost Update Problem:** Occurs when two transactions modify the same data at the same time, but one overwrites the other’s changes without awareness.

2. **Dirty Read:** Occurs when a transaction reads uncommitted changes from another transaction.

3. **Non-Repeatable Read:** Occurs when a transaction reads the same data twice and gets different values because another transaction modified it.

4. **Phantom Read:** Occurs when a transaction reads a set of rows, but another transaction adds or removes rows, changing the results of a later query.

### Security Problems

Not every user of the **database system** should have access to **all the data**. Proper access control mechanisms must be enforced to protect sensitive information.

#### Common Security Issues

1. **Unauthorized Access:** Without proper authentication and access controls, unauthorized users might access sensitive data.

2. **Data Leaks and Breaches:** Poor security measures can expose sensitive data to hackers or insiders.

3. **SQL Injection Attacks:** Attackers manipulate input fields to execute harmful SQL queries.

4. **Privilege Escalation:** A user with low privileges gains unauthorized access to higher-privilege data.

5. **Weak Authentication Mechanisms:** Simple passwords or lack of multi-factor authentication (MFA) make the system vulnerable.

## View of Data
