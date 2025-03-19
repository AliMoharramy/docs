---
sidebar_label: "chapter 1"
sidebar_position: 1
---

# Chapter 1

A **database-management system (DBMS)** is a collection of interrelated data and a set of programs to access those data.  
The primary goal of a DBMS is to provide a way to store and retrieve database information that is both **convenient and efficient**.

## Purpose of Database Systems

### Data Redundancy and Inconsistency

Since different programmers create the files and application programs over a long period, the various files are likely to have different structures, and the programs may be written in several programming languages. Moreover, the same information may be duplicated in several places (files).

For example, if a student has a double major (say, music and mathematics), their address and telephone number may appear in multiple department records. This redundancy leads to:

- Higher storage and access costs.
- Data inconsistency (e.g., a changed address is updated in the Music department but not elsewhere).

### Difficulty in Accessing Data

Traditional **file-processing systems** make data retrieval difficult. If a university clerk needs a specific student list (e.g., by postal code), no pre-existing program may be available. They must either:

- Filter data manually.
- Request a new program (time-consuming).

Each new query requires additional programming, making the system inefficient. A **DBMS** provides a **more responsive and flexible** data retrieval system.

### Integrity Problems

The **data values stored** in the database must satisfy certain consistency constraints. If constraints are not properly enforced, invalid or inconsistent data may exist in the system.

### Atomicity Problems

A computer system, like any other device, is subject to **failure**. In many applications, it is crucial that if a failure occurs, the data be **restored** to the **consistent state** that existed prior to the failure.

### Concurrent-Access Anomalies

When multiple users update data simultaneously, **inconsistencies** may occur. For example:

- If two clerks debit an account at the same time, the final balance might be incorrect.
- If two students register for a course at the same time, the count may not update correctly.

To prevent these issues, **concurrency control** methods like **locking** and **transactions** should be used in database systems.

### Security Problems

Not every user of the **database system** should have access to **all the data**. Proper access control mechanisms must be enforced to protect sensitive information.
