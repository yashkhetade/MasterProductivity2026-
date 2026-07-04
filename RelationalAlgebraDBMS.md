# Introduction to Relational Algebra in DBMS

LINK - https://www.geeksforgeeks.org/dbms/introduction-of-relational-algebra-in-dbms/


# Chapter 1: Introduction to Relational Algebra (RA)
## GATE CSE + IBPS SO IT Officer Complete Notes

---

# Chapter Overview

After studying this chapter, you will be able to answer questions like:

- What is Relational Algebra?
- Why is it needed?
- Why is it called Procedural Query Language?
- Difference between SQL and Relational Algebra
- Difference between Relational Algebra and Relational Calculus
- Where is Relational Algebra used?
- Why do GATE and IBPS ask Relational Algebra questions?
- How are Relational Algebra questions solved?
- How are SQL queries converted into Relational Algebra?

---

# 1. What is Relational Algebra?

Relational Algebra (RA) is a **formal query language** used to retrieve data from relational databases.

It tells the database:

> **WHAT operations should be performed on relations (tables) and IN WHICH ORDER.**

Think of it as **Mathematics of Databases**.

It works on **Relations (Tables)** and produces another **Relation (Table)** as output.

---

## Simple Definition (Exam Definition)

> Relational Algebra is a procedural query language that performs operations on one or more relations and always returns another relation.

**Remember this definition.**

Many competitive exams ask this directly.

---

# 2. Why was Relational Algebra Introduced?

Suppose we have this table:

Employee

| EmpID | Name | Salary |
|------|------|---------|
|101|Amit|40000|
|102|Rahul|70000|
|103|Neha|55000|

Suppose we want

> Find employees whose salary is greater than 50,000.

How should the database perform this?

There must be some mathematical operations.

These operations are provided by **Relational Algebra**.

---

Without Relational Algebra

```
Database
   ↓
No mathematical operations
   ↓
Cannot process queries efficiently
```

With Relational Algebra

```
Database
   ↓
Selection
Projection
Join
Union
Difference
Product
Division
   ↓
Desired Result
```

---

# 3. Who Developed Relational Algebra?

Relational Algebra was proposed by

> **Dr. Edgar F. Codd**

He is known as

> **Father of Relational Database**

He introduced the Relational Model in **1970**.

Almost every database today is based on his ideas.

Examples

- Oracle
- MySQL
- PostgreSQL
- SQL Server
- DB2

---

# 4. Why is it called Relational Algebra?

Let's understand each word.

## Relation

Relation means

> Table

Example

Student

| Roll | Name | Marks |
|------|------|--------|
|1|Ram|80|
|2|Shyam|90|

This table is called a Relation.

---

## Algebra

Algebra means

Performing operations.

For example

```
5 + 3

a × b

x - y
```

Similarly

Relational Algebra performs operations on tables.

Instead of

```
5 + 3
```

we do

```
Student
JOIN
Marks
```

or

```
Project(Student)
```

Hence

Relation + Algebra

=

Relational Algebra

---

# 5. Real Life Analogy

Imagine a library.

Books are stored on shelves.

Suppose someone asks

> Give me all books written by Abdul Kalam.

What will the librarian do?

Step 1

Look at all books.

↓

Step 2

Check Author column.

↓

Step 3

Select matching books.

↓

Step 4

Return results.

This process is exactly what Relational Algebra does.

---

# 6. Why is Relational Algebra Important?

Because SQL internally converts queries into Relational Algebra.

Example

SQL

```sql
SELECT Name
FROM Employee
WHERE Salary > 50000;
```

Internally database thinks like this

```
Project(Name)

Selection(Salary>50000)

Employee
```

The database optimizer works using Relational Algebra.

Therefore,

Understanding RA means understanding how SQL actually works.

---

# 7. Where is Relational Algebra Used?

Many students think

"I never write Relational Algebra."

Correct.

Users usually write SQL.

But internally

```
SQL

↓

Parser

↓

Relational Algebra

↓

Optimization

↓

Execution Plan

↓

Database Output
```

Every DBMS uses Relational Algebra concepts.

---

# 8. Characteristics of Relational Algebra

These are favorite exam questions.

### 1. Procedural Language

It tells

**How** to retrieve data.

---

### 2. Operates on Relations

Input

Relation

Output

Relation

---

### 3. Closed under Operations

Output of every operation

↓

is again a Relation.

This property is called

> Closure Property

Very important for GATE.

---

### 4. Uses Mathematical Set Theory

Relational Algebra is based on

- Sets
- Cartesian Product
- Union
- Difference
- Intersection

---

### 5. Duplicate Tuples are Not Allowed

Relations are sets.

Sets never contain duplicates.

Therefore

Duplicate rows are removed.

---

### 6. Order Does Not Matter

These two relations are considered identical.

Relation A

|ID|
|--|
|1|
|2|
|3|

Relation B

|ID|
|--|
|3|
|1|
|2|

Same relation.

---

### 7. Attributes have Unique Names

Example

Good

```
Employee(EmpID, Name, Salary)
```

Bad

```
Employee(ID, ID, Salary)
```

---

# 9. Procedural Language Meaning

One of the most asked questions.

Suppose someone asks

> Make tea.

Non-Procedural

```
Bring me tea.
```

No steps.

---

Procedural

```
Boil water

↓

Add tea

↓

Add sugar

↓

Add milk

↓

Filter

↓

Serve
```

All steps are specified.

Relational Algebra also specifies all operations.

Hence

Procedural Language.

---

# 10. Relational Algebra vs SQL

| Relational Algebra | SQL |
|--------------------|-----|
| Procedural | Declarative |
| Mathematical | Practical |
| Theoretical | Commercial |
| Used internally | Used by users |
| Uses symbols | Uses English keywords |

Example

Relational Algebra

```
π Name

σ Salary>50000

Employee
```

SQL

```sql
SELECT Name
FROM Employee
WHERE Salary>50000;
```

---

# 11. Relational Algebra vs Relational Calculus

Students confuse these.

Remember

## Relational Algebra

Procedural

Tells

HOW

---

## Relational Calculus

Non-Procedural

Tells

WHAT

---

Easy Trick

```
Algebra

↓

Algorithm

↓

Procedure

↓

HOW
```

```
Calculus

↓

Condition

↓

WHAT
```

---

# 12. Basic Components

Relational Algebra works with

Relation

↓

Tuple

↓

Attribute

---

Relation

Table

---

Tuple

Row

---

Attribute

Column

---

Example

Employee

|ID|Name|Salary|
|--|----|------|
|101|Amit|40000|
|102|Neha|60000|

Relation

Employee

Attributes

ID

Name

Salary

Tuples

(101,Amit,40000)

(102,Neha,60000)

---

# 13. Closure Property

Very important.

Suppose

Employee

↓

Selection

↓

Output

Output is again

Employee-like relation.

Example

Input

|ID|Salary|
|--|------|
|1|40000|
|2|70000|

Selection Salary>50000

Output

|ID|Salary|
|--|------|
|2|70000|

Output is still a relation.

Hence

Closure Property.

---

# 14. Why Closure Property is Useful?

Because operations can be chained.

Example

```
Selection

↓

Projection

↓

Join

↓

Difference

↓

Union
```

Every output becomes input for next operation.

Without Closure Property this would be impossible.

---

# 15. Building Blocks of Relational Algebra

There are six fundamental operators.

| Operator | Symbol |
|-----------|--------|
| Select | σ |
| Project | π |
| Union | ∪ |
| Difference | − |
| Cartesian Product | × |
| Rename | ρ |

Everything else is derived from these.

---

# 16. Derived Operators

Built using basic operators.

Examples

- Join
- Natural Join
- Theta Join
- Equi Join
- Outer Join
- Semi Join
- Division
- Intersection

These are heavily asked in GATE.

---

# 17. Important Symbols

| Symbol | Meaning |
|---------|----------|
|σ|Selection|
|π|Projection|
|ρ|Rename|
|∪|Union|
|−|Difference|
|×|Cartesian Product|
|⋈|Join|
|÷|Division|
|∩|Intersection|

Memorize these symbols—they are used directly in exam questions.

---

# 18. How GATE Asks Relational Algebra Questions

Common patterns include:

1. Output of an RA expression.
2. Number of tuples after an operation.
3. Equivalent SQL for a given RA expression.
4. Equivalent RA for a given SQL query.
5. Join-based expressions.
6. Set operation conditions.
7. Closure property.
8. Procedural vs declarative.
9. Keys involved in joins.
10. Difference between operators.

---

# 19. How IBPS SO IT Officer Asks Relational Algebra Questions

IBPS generally asks conceptual questions such as:

- RA is based on which mathematical concept?
- Which language is procedural?
- Which operator removes columns?
- Which operator removes rows?
- Output of projection?
- Difference between selection and projection?
- Symbol of join?
- Symbol of projection?
- Closure property.

These are usually easier than GATE but require conceptual clarity.

---

# 20. Memory Tricks (Mnemonics)

### Trick 1: RA Characteristics

**P C S D O**

Remember:

> **"Please Cook Simple Delicious Omelette"**

- **P** = Procedural
- **C** = Closure property
- **S** = Set-based
- **D** = Duplicate-free
- **O** = Order doesn't matter

---

### Trick 2: Basic Operators

Remember:

> **"Some People Use Different Cars Regularly"**

- **S** = Selection (σ)
- **P** = Projection (π)
- **U** = Union (∪)
- **D** = Difference (−)
- **C** = Cartesian Product (×)
- **R** = Rename (ρ)

---

# 21. Exam Tips

- Always remember: **Relation = Table**
- **Tuple = Row**
- **Attribute = Column**
- **Selection filters rows**
- **Projection selects columns**
- Every RA operation returns another relation (Closure Property).
- RA is procedural; SQL is declarative.
- RA is based on set theory, so duplicates are eliminated.

---

# Chapter 1 Summary

- Relational Algebra is a procedural query language.
- It operates on relations (tables) and returns relations.
- Proposed by Dr. Edgar F. Codd.
- It is the mathematical foundation of relational databases.
- SQL queries are internally translated into Relational Algebra by the DBMS.
- RA follows the Closure Property.
- Duplicate tuples are not allowed.
- Order of tuples is irrelevant.
- Six basic operators form the foundation of all other operations.
- GATE emphasizes expression evaluation and operator combinations.
- IBPS SO emphasizes concepts, definitions, symbols, and differences.

---

# Quick Revision (1 Minute)

| Question | Answer |
|----------|--------|
|Relation|Table|
|Tuple|Row|
|Attribute|Column|
|RA Type|Procedural|
|SQL Type|Declarative|
|Returns|Relation|
|Based On|Set Theory|
|Duplicates Allowed?|No|
|Order Important?|No|
|Father of RDBMS|Edgar F. Codd|
|Most Important Property|Closure Property|
|Basic Operators|σ, π, ∪, −, ×, ρ|

---

# What's Next?

**Chapter 2: Relations, Tuples, Attributes, Domains, Schema, Instance, Degree, Cardinality, Null Values, Keys, and Set Theory Foundations** — these concepts are essential before learning the individual Relational Algebra operators.

# Chapter 2: Relations, Tuples, Attributes, Domains, Schema, Instance, Degree, Cardinality & Set Theory
## Complete Notes for GATE CSE + IBPS SO IT Officer
### Relational Algebra Foundation

---

# Chapter Overview

This chapter is the **foundation of Relational Algebra**.

Almost every Relational Algebra question starts with a relation like:

```
Employee(EmpID, Name, Dept, Salary)
```

or

```
Student(RollNo, Name, Branch)
```

Unless you understand what a **relation**, **attribute**, **tuple**, **schema**, **instance**, **degree**, and **cardinality** are, solving RA questions becomes difficult.

This chapter explains all these concepts in the simplest language with examples.

---

# 1. What is a Relation?

The word **Relation** simply means:

> **A Table in a Relational Database.**

### Example

Employee

| EmpID | Name | Department | Salary |
|-------|------|------------|-------:|
|101|Rahul|IT|50000|
|102|Amit|HR|45000|
|103|Neha|Finance|60000|

This complete table is called a **Relation**.

---

## Important Points

- Relation = Table
- Relation has rows and columns.
- Relation stores data.
- Every RA operator takes one or more relations as input.
- Every RA operator returns another relation.

---

### Exam Point

**Relation is NOT a database.**

A database contains many relations.

Example

```
Company Database

│
├── Employee
├── Department
├── Project
├── Salary
└── Attendance
```

Each table is a **Relation**.

---

# 2. What is a Tuple?

A Tuple means

> One complete row of a relation.

Example

Employee

|EmpID|Name|Department|Salary|
|----|----|----------|------|
|101|Rahul|IT|50000|
|102|Amit|HR|45000|
|103|Neha|Finance|60000|

Tuple 1

```
(101, Rahul, IT, 50000)
```

Tuple 2

```
(102, Amit, HR, 45000)
```

Tuple 3

```
(103, Neha, Finance, 60000)
```

Each row = One Tuple

---

### Easy Trick

Imagine an attendance register.

Each student's complete information in one row is a tuple.

---

# 3. What is an Attribute?

An Attribute means

> A Column of a table.

Example

Employee

|EmpID|Name|Department|Salary|
|----|----|----------|------|

Attributes are

- EmpID
- Name
- Department
- Salary

---

### Easy Trick

Column = Attribute

Row = Tuple

Table = Relation

---

# 4. Relation = Collection of Tuples

Mathematically

```
Relation

=

Set of Tuples
```

Example

Employee

```
{
(101,Rahul,IT,50000),

(102,Amit,HR,45000),

(103,Neha,Finance,60000)

}
```

Notice the word **SET**.

Therefore

Duplicate tuples are NOT allowed.

---

# 5. Domain

Very important for GATE.

## Definition

A Domain is

> The set of all possible values that an attribute can take.

Example

Attribute

Age

Possible values

```
18

19

20

...

60
```

This collection is called Domain.

---

Another Example

Gender

Possible values

```
Male

Female

Other
```

This is also a domain.

---

Employee

|EmpID|Name|Department|
|----|----|----------|

Domains

EmpID

```
Positive Integers
```

Name

```
Strings
```

Department

```
IT

HR

Finance

Sales
```

---

### Why Domain is Important?

Suppose

Age

Domain

```
18-60
```

Can Age be

```
Blue
```

No.

Can Age be

```
Apple
```

No.

Because it violates the domain.

---

### Exam Definition

> Domain is the set of permissible values for an attribute.

---

# 6. Relation Schema

Very Important.

Many students confuse Schema with Instance.

---

Schema means

> Structure of a Relation.

Example

```
Employee(

EmpID,

Name,

Department,

Salary

)
```

Only column names.

No data.

This is Relation Schema.

---

Another Example

```
Student(

RollNo,

Name,

Branch,

Marks

)
```

Again

Only structure.

---

### Easy Trick

Schema

=

Blueprint

Instance

=

Actual Building

---

# 7. Relation Instance

Instance means

> Actual data stored inside a relation at a particular time.

Example

Schema

```
Employee(

EmpID,

Name,

Salary

)
```

Instance

|EmpID|Name|Salary|
|----|----|------|
|101|Rahul|50000|
|102|Amit|45000|

Tomorrow

|EmpID|Name|Salary|
|----|----|------|
|101|Rahul|52000|
|102|Amit|47000|
|103|Neha|60000|

Schema

Same

Instance

Changed

---

### Memory Trick

Schema

Never changes frequently.

Instance

Changes every day.

---

# 8. Degree of Relation

Degree means

> Number of Attributes (Columns)

Example

|ID|Name|Age|Dept|

Columns

ID

Name

Age

Dept

Total columns

4

Degree

4

---

Another Example

|A|B|C|

Degree

3

---

### Formula

```
Degree

=

Number of Columns
```

---

# 9. Cardinality of Relation

Cardinality means

> Number of Tuples (Rows)

Example

|ID|Name|
|--|----|
|1|A|
|2|B|
|3|C|
|4|D|

Rows

4

Cardinality

4

---

### Formula

```
Cardinality

=

Number of Rows
```

---

# Degree vs Cardinality

Most Asked Question

|Degree|Cardinality|
|--------|------------|
|Columns|Rows|
|Structure|Data|
|Usually Fixed|Changes Frequently|

---

Example

|ID|Name|Age|

Rows

100

Degree

3

Cardinality

100

---

# Memory Trick

Degree

↓

Across

↓

Columns

Cardinality

↓

Down

↓

Rows

---

# 10. Database Schema vs Relation Schema

Database Schema

Contains all tables.

```
College Database

Student

Faculty

Department

Hostel

Library
```

Relation Schema

Only one table.

```
Student(

Roll,

Name,

Branch

)
```

---

# 11. Relation Properties

Every relation follows these rules.

---

## Property 1

Rows are unique.

Duplicate tuples are not allowed.

Wrong

|ID|Name|
|--|----|
|1|A|
|1|A|

Correct

Duplicates removed.

---

## Property 2

Order of rows doesn't matter.

These two relations are identical.

```
1

2

3
```

and

```
3

1

2
```

---

## Property 3

Order of columns doesn't matter mathematically, though attribute names identify meaning.

---

## Property 4

Each cell contains exactly one value.

Wrong

|Phone|
|------|
|111,222|

Correct

Each cell contains one atomic value (First Normal Form principle).

---

## Property 5

Each attribute has a unique name.

Correct

```
ID

Name

Salary
```

Wrong

```
ID

ID

Salary
```

---

# 12. Null Values

NULL means

> Unknown or Missing value.

Example

|ID|Name|Phone|
|--|----|------|
|101|Rahul|NULL|

Phone is unknown.

NULL

does NOT mean

0

does NOT mean

Empty String

does NOT mean

False

---

### GATE Trick

NULL ≠ 0

NULL ≠ Blank

NULL = Unknown

---

# 13. Candidate Key

A Candidate Key is

> A minimal attribute (or set of attributes) that uniquely identifies every tuple.

Example

Student

|Roll|Aadhar|Name|
|----|------|----|

Roll

Unique

Aadhar

Unique

Both are Candidate Keys.

---

# 14. Primary Key

One Candidate Key chosen as the main identifier.

Example

Candidate Keys

```
Roll

Aadhar
```

Choose

Roll

Primary Key

---

# 15. Super Key

Any attribute set that uniquely identifies rows.

Example

Student

```
Roll
```

Super Key

```
Roll

Roll + Name

Roll + Branch

Roll + Age
```

All are Super Keys.

But only

Roll

is minimal.

Hence Candidate Key.

---

# 16. Foreign Key

Attribute referring to another table's Primary Key.

Department

|DeptID|DeptName|
|------|--------|
|10|IT|
|20|HR|

Employee

|EmpID|DeptID|
|-----|------|
|1|10|
|2|20|

Employee.DeptID

Foreign Key

---

# 17. Why Keys Matter in Relational Algebra?

Most JOIN operations are based on keys.

Example

Employee

```
DeptID
```

Department

```
DeptID
```

Natural Join matches these values.

---

# 18. Set Theory Basics

Relational Algebra is based on Set Theory.

Remember

```
Relation

=

Set of Tuples
```

---

Important Set Operations

Union

Difference

Intersection

Cartesian Product

These become RA operators.

---

# 19. Ordered Pair vs Relation

Example

```
(1,A)

(2,B)
```

These are tuples.

Many tuples together form a relation.

---

# 20. Real-Life Analogy

Imagine an Excel sheet.

Columns

↓

Attributes

Rows

↓

Tuples

Whole Sheet

↓

Relation

Workbook

↓

Database

---

# 21. Common GATE Questions

### Q1

What is the degree?

Count columns.

---

### Q2

What is the cardinality?

Count rows.

---

### Q3

Schema or Instance?

Only column names

↓

Schema

Contains data

↓

Instance

---

### Q4

Which changes frequently?

Instance

---

### Q5

Relation is based on?

Set Theory

---

# 22. IBPS SO Important One-Liners

- Relation = Table
- Tuple = Row
- Attribute = Column
- Degree = Number of Columns
- Cardinality = Number of Rows
- Schema = Structure
- Instance = Actual Data
- Domain = Allowed Values
- NULL = Unknown Value
- Candidate Key = Minimal Unique Identifier
- Primary Key = Selected Candidate Key
- Foreign Key = Reference to Another Table
- Super Key = Any Unique Attribute Set

---

# 23. Memory Mnemonics

## D → Degree → Dimension Across (Columns)

Think:

```
Degree

=

Width
```

---

## C → Cardinality → Count Down (Rows)

Think:

```
Cardinality

=

Height
```

---

## S → Schema → Skeleton

Only structure.

---

## I → Instance → Information

Actual data.

---

# 24. Practice Questions

### Q1

A relation has 8 attributes and 120 tuples.

Degree?

**Answer:** 8

---

### Q2

A relation has 15 rows and 4 columns.

Cardinality?

**Answer:** 15

Degree?

**Answer:** 4

---

### Q3

Which changes more frequently?

A. Schema

B. Instance

**Answer:** Instance

---

### Q4

Which is based on Set Theory?

**Answer:** Relational Algebra

---

### Q5

NULL means?

A. Zero

B. Empty

C. Unknown

D. False

**Answer:** C

---

# Chapter Summary

- Relation = Table
- Tuple = Row
- Attribute = Column
- Domain = Allowed values of an attribute
- Schema = Table structure
- Instance = Actual data at a specific time
- Degree = Number of columns
- Cardinality = Number of rows
- Relations follow set properties (no duplicate tuples, order of rows doesn't matter)
- NULL represents an unknown or missing value
- Candidate Key uniquely identifies tuples with minimal attributes
- Primary Key is the selected Candidate Key
- Foreign Key links relations
- Set Theory is the mathematical foundation of Relational Algebra

---

# Quick Revision Table

| Concept | Remember |
|---------|----------|
|Relation|Table|
|Tuple|Row|
|Attribute|Column|
|Domain|Allowed Values|
|Schema|Structure|
|Instance|Actual Data|
|Degree|Columns|
|Cardinality|Rows|
|Primary Key|Chosen Candidate Key|
|Candidate Key|Minimal Unique Identifier|
|Super Key|Any Unique Identifier|
|Foreign Key|Reference to Primary Key|
|NULL|Unknown|
|Foundation of RA|Set Theory|
|Duplicate Tuples|Not Allowed|
|Order of Rows|Not Important|

---

## Next Chapter

**Chapter 3: Set Theory for Relational Algebra**  
You'll learn Union, Intersection, Difference, Cartesian Product, compatibility conditions, Venn diagrams, and how these mathematical concepts directly translate into Relational Algebra operators and GATE/IBPS exam questions.


# Chapter 3: Set Theory for Relational Algebra (RA)
## Complete Notes for GATE CSE + IBPS SO IT Officer
### The Mathematical Foundation of Relational Algebra

---

# Chapter Overview

Before learning Relational Algebra operators like:

- Union (∪)
- Difference (−)
- Intersection (∩)
- Cartesian Product (×)
- Join (⋈)

you **must** understand Set Theory because **Relational Algebra is based on Set Theory**.

> **Important Exam Fact**
>
> Almost every GATE and IBPS SO question on Relational Algebra uses concepts from Set Theory either directly or indirectly.

---

# Learning Outcomes

After this chapter, you will be able to:

- Understand what a Set is
- Understand why a Relation is considered a Set
- Solve Union questions
- Solve Difference questions
- Solve Intersection questions
- Solve Cartesian Product questions
- Understand Union Compatibility
- Solve GATE-style numerical questions
- Avoid common mistakes

---

# 1. What is a Set?

A **Set** is

> A well-defined collection of distinct objects.

The important word is

> **Distinct**

which means

> **No duplicates**

---

## Example

```
A = {1,2,3,4}
```

Valid Set

---

```
A = {1,2,2,3}
```

Mathematically

```
A = {1,2,3}
```

Duplicate 2 is automatically removed.

---

## Database Connection

A relation is also a Set.

Therefore,

Duplicate tuples are **not allowed**.

---

Example

Employee

|ID|Name|
|--|----|
|1|Rahul|
|2|Amit|
|2|Amit|

This is **not** a valid relation.

Correct relation

|ID|Name|
|--|----|
|1|Rahul|
|2|Amit|

---

# 2. Why is Relation Called a Set?

Because every relation follows Set properties.

Properties inherited from Set Theory:

- No duplicate tuples
- Order of tuples doesn't matter
- Set operations can be applied
- Mathematical reasoning becomes possible

---

# 3. Important Set Terminology

Suppose

```
A = {1,2,3}

B = {3,4,5}
```

Elements

```
1

2

3
```

are members of Set A.

Notation

```
2 ∈ A
```

means

2 belongs to A.

---

```
5 ∉ A
```

means

5 does not belong to A.

---

# 4. Empty Set

Empty Set

Contains no elements.

Notation

```
∅
```

or

```
{}
```

Example

Students having age > 200

Result

```
∅
```

---

# 5. Universal Set

Universal Set

Contains all possible elements.

Example

```
U = {1,2,3,4,5,6,7,8}
```

Not used directly in Relational Algebra but useful for understanding complements in mathematics.

---

# 6. Subset

Suppose

```
A = {1,2,3}

B = {1,2,3,4,5}
```

Every element of A exists in B.

Therefore

```
A ⊆ B
```

A is a subset of B.

---

Database Example

Employee IDs

```
{1,2}
```

All Employees

```
{1,2,3,4,5}
```

First is a subset.

---

# 7. Equality of Sets

Two sets are equal if

- They contain the same elements.
- Order does not matter.

Example

```
A = {1,2,3}

B = {3,2,1}
```

A = B

---

# 8. Union

Most Important.

Symbol

```
∪
```

Meaning

Combine both sets.

---

Example

```
A = {1,2,3}

B = {3,4,5}
```

Union

```
A ∪ B

=

{1,2,3,4,5}
```

Notice

Duplicate 3 appears only once.

---

## Relation Example

R

|ID|
|--|
|1|
|2|
|3|

S

|ID|
|--|
|3|
|4|
|5|

Result

|ID|
|--|
|1|
|2|
|3|
|4|
|5|

---

# 9. Memory Trick for Union

Think

```
School A

+

School B

=

All Students
```

Combine everything.

---

# 10. Intersection

Symbol

```
∩
```

Meaning

Common elements.

---

Example

```
A = {1,2,3}

B = {3,4,5}
```

Result

```
{3}
```

Only common element.

---

## Relation Example

R

|ID|
|--|
|1|
|2|
|3|

S

|ID|
|--|
|2|
|3|
|4|

Intersection

|ID|
|--|
|2|
|3|

---

# 11. Memory Trick

Intersection

↓

Common

Think

Students studying in

Engineering

AND

MBA

Common students only.

---

# 12. Difference

Symbol

```
−
```

Meaning

Elements present in first set but NOT in second.

---

Example

```
A = {1,2,3,4}

B = {3,4,5}
```

```
A − B

=

{1,2}
```

---

Notice

```
B − A

=

{5}
```

Difference is **not commutative**.

---

Database Example

Employees

minus

Managers

Result

Employees who are not Managers.

---

# 13. Cartesian Product

Symbol

```
×
```

Most Important for Join.

---

Example

```
A = {1,2}

B = {X,Y}
```

Result

```
(1,X)

(1,Y)

(2,X)

(2,Y)
```

Every element pairs with every other element.

---

Formula

```
|A × B|

=

|A|

×

|B|
```

---

Example

R has

5 rows

S has

10 rows

Cartesian Product

```
5 × 10

=

50 rows
```

Favorite GATE question.

---

# 14. Venn Diagram Summary (Conceptual)

```
Union
Everything from both sets

Intersection
Only common region

Difference
Only left side after removing common elements
```

Imagine two overlapping circles:

- Union = entire area of both circles.
- Intersection = overlapping area.
- Difference = left circle excluding overlap.

---

# 15. Union Compatibility

Very Important.

Two relations can be unioned only if

### Condition 1

Same number of attributes.

---

### Condition 2

Corresponding attributes have compatible domains (same or compatible data types).

---

Example

R

|ID|Name|

S

|Roll|StudentName|

Allowed (if domains correspond).

---

Wrong Example

R

|ID|Name|

S

|ID|

Not Allowed.

Different number of columns.

---

# 16. Why Union Compatibility?

Suppose

Employee

|ID|Name|

Project

|PID|Budget|Location|

Can we union them?

No.

Structures differ.

The DBMS cannot combine incompatible relations meaningfully.

---

# 17. Set Operations in Relational Algebra

| Set Theory | Relational Algebra |
|------------|--------------------|
| Union | Union (∪) |
| Difference | Difference (−) |
| Intersection | Intersection (∩) *(derived operator)* |
| Cartesian Product | Cartesian Product (×) |

---

# 18. Cardinality Rules

Suppose

```
|R| = 20

|S| = 10
```

Maximum rows after Union

```
20 + 10 = 30
```

(if no duplicates)

Minimum

```
20
```

(if S is a subset of R)

---

Intersection

Maximum

```
min(20,10)

=

10
```

Minimum

```
0
```

---

Difference

Maximum

```
20
```

Minimum

```
0
```

---

Cartesian Product

```
20 × 10

=

200
```

Always exact.

---

# 19. Common Exam Tricks

### Trick 1

Union removes duplicates.

---

### Trick 2

Difference is directional.

```
A−B ≠ B−A
```

---

### Trick 3

Cartesian Product creates every possible pair.

---

### Trick 4

Intersection returns only common tuples.

---

### Trick 5

Relations are sets.

Therefore,

Duplicates never appear in the final result.

---

# 20. Solved Examples

## Example 1

```
R = {1,2,3}

S = {3,4,5}
```

Union

```
{1,2,3,4,5}
```

---

## Example 2

Intersection

```
{3}
```

---

## Example 3

Difference

```
R−S

=

{1,2}
```

---

## Example 4

```
|R|=7

|S|=9
```

Cartesian Product

```
63
```

---

## Example 5

R

|ID|
|--|
|1|
|2|
|3|

S

|ID|
|--|
|2|
|3|

Difference

|ID|
|--|
|1|

---

# 21. GATE-Level Practice Questions

### Q1

If

```
|R|=6

|S|=8
```

Find

```
|R × S|
```

Answer

```
48
```

---

### Q2

Maximum tuples in

```
R ∪ S
```

if

```
|R|=12

|S|=15
```

Answer

```
27
```

---

### Q3

Minimum tuples in

```
R ∩ S
```

Answer

```
0
```

---

### Q4

Maximum tuples in

```
R ∩ S
```

```
|R|=5

|S|=10
```

Answer

```
5
```

---

### Q5

Which operation requires Union Compatibility?

A. Selection

B. Projection

C. Union

D. Cartesian Product

**Answer:** C

---

### Q6

Which operation always produces exactly |R| × |S| tuples?

A. Union

B. Difference

C. Cartesian Product

D. Projection

**Answer:** C

---

# 22. IBPS SO One-Liners

- Relation is a Set of tuples.
- Duplicate tuples are not allowed.
- Union combines relations.
- Intersection finds common tuples.
- Difference removes matching tuples.
- Cartesian Product pairs every tuple with every other tuple.
- Union requires Union Compatibility.
- Cartesian Product does **not** require Union Compatibility.
- Difference also requires Union Compatibility because both relations must have comparable structures.

---

# 23. Mnemonics

### U → Union → Unite

Everything together.

---

### I → Intersection → Interact

Common part only.

---

### D → Difference → Delete

Remove second set from first.

---

### C → Cartesian Product → Combination

Every possible combination.

---

# 24. Common Mistakes

❌ Thinking Union keeps duplicates.

✔ Union removes duplicates.

---

❌ Thinking Difference is commutative.

✔

```
A−B ≠ B−A
```

---

❌ Thinking Cartesian Product removes duplicates.

✔ It simply creates all combinations. Duplicate elimination (if any) follows relation semantics.

---

❌ Thinking Union works on any two tables.

✔ Both relations must be Union Compatible.

---

# 25. Chapter Summary

- Relational Algebra is based on Set Theory.
- A relation behaves like a mathematical set.
- Duplicate tuples are not allowed.
- Union combines tuples from both relations.
- Intersection returns only common tuples.
- Difference returns tuples present in the first relation but absent in the second.
- Cartesian Product pairs every tuple of one relation with every tuple of the other.
- Union and Difference require Union Compatibility.
- Cartesian Product size = |R| × |S|.
- These concepts are used extensively in GATE and IBPS SO questions.

---

# Quick Revision Table

| Concept | Key Point |
|----------|-----------|
| Set | Collection of distinct elements |
| Relation | Set of tuples |
| Union (∪) | Combine relations, remove duplicates |
| Intersection (∩) | Common tuples |
| Difference (−) | First minus second |
| Cartesian Product (×) | All possible pairs |
| Union Compatibility | Same number of attributes and compatible domains |
| Cartesian Product Size | \|R\| × \|S\| |
| Difference Property | Not commutative |
| Duplicate Tuples | Never allowed in a relation |

---

# What's Next?

## Chapter 4: Basic Relational Algebra Operators

In the next chapter, you'll learn the **six fundamental operators** of Relational Algebra in depth:

1. Selection (σ)
2. Projection (π)
3. Rename (ρ)
4. Union (∪)
5. Difference (−)
6. Cartesian Product (×)

Each operator will include:
- Definition
- Syntax
- Step-by-step evaluation
- Multiple solved examples
- GATE tricks
- IBPS SO shortcuts
- Common mistakes
- Exam-level practice questions


# Chapter 4: Basic Relational Algebra Operators
## GATE CSE + IBPS SO IT Officer Complete Notes

---

# Chapter Overview

In this chapter, we will study the **6 Fundamental (Primitive) Operators** of Relational Algebra.

These operators are the building blocks of all other operators.

```
Basic Operators

        Relational Algebra
              │
 ┌────────────┼────────────┐
 │            │            │
Selection   Projection   Rename
   σ             π          ρ
 │            │
 ├────────────┼────────────┐
 │                         │
Union (∪)          Difference (−)
 │
Cartesian Product (×)
```

> **Exam Tip:** Every complex Relational Algebra expression is built using these six operators.

---

# Primitive Operators

| Operator | Symbol | Purpose |
|----------|---------|----------|
| Selection | σ | Select Rows |
| Projection | π | Select Columns |
| Rename | ρ | Rename Relation/Attributes |
| Union | ∪ | Combine Relations |
| Difference | − | Subtract Relations |
| Cartesian Product | × | Pair Every Tuple |

---

# 1. Selection (σ)

## Definition

Selection is used to **select rows (tuples)** satisfying a condition.

Think of it as applying a filter.

---

## Symbol

```
σ
```

Pronounced as

> Sigma

---

## Syntax

```
σ Condition (Relation)
```

Example

```
σ Salary > 50000 (Employee)
```

Meaning

> Select all employees having salary greater than 50,000.

---

## Example Relation

Employee

| EmpID | Name | Dept | Salary |
|------|------|------|-------:|
|101|Rahul|IT|50000|
|102|Amit|HR|45000|
|103|Neha|IT|65000|
|104|Pooja|Sales|40000|

Query

```
σ Salary > 50000(Employee)
```

Result

|EmpID|Name|Dept|Salary|
|----|----|----|------|
|103|Neha|IT|65000|

---

## Multiple Conditions

```
σ Dept='IT' AND Salary>50000(Employee)
```

Result

|EmpID|Name|Dept|Salary|
|----|----|----|------|
|103|Neha|IT|65000|

---

## Allowed Operators

```
=

≠

>

<

>=

<=
```

Logical Operators

```
AND

OR

NOT
```

---

## Selection Formula

```
Input

↓

Apply Condition

↓

Output Rows
```

Rows are reduced.

Columns remain unchanged.

---

## Important Property

Selection **never changes columns**.

It only removes rows.

---

## Memory Trick

Selection

↓

Select Students

↓

Rows

Think

Teacher says

> "Only students scoring above 90 may stand."

Students (rows) reduce.

Columns stay the same.

---

# GATE Question

Employee

|ID|Salary|
|--|------|
|1|20000|
|2|60000|
|3|70000|

Find

```
σ Salary>50000(Employee)
```

Answer

|ID|Salary|
|--|------|
|2|60000|
|3|70000|

---

# 2. Projection (π)

## Definition

Projection selects **required columns (attributes).**

---

## Symbol

```
π
```

Pronounced

Pi

---

## Syntax

```
π AttributeList(Relation)
```

Example

```
π Name(Employee)
```

---

## Example

Employee

|ID|Name|Dept|Salary|
|--|----|----|------|
|101|Rahul|IT|50000|
|102|Amit|HR|45000|
|103|Neha|IT|65000|

Query

```
π Name(Employee)
```

Result

|Name|
|----|
|Rahul|
|Amit|
|Neha|

---

## Multiple Columns

```
π Name,Dept(Employee)
```

Result

|Name|Dept|
|----|----|
|Rahul|IT|
|Amit|HR|
|Neha|IT|

---

## Duplicate Elimination

Very Important.

Employee

|Dept|
|----|
|IT|
|HR|
|IT|

Query

```
π Dept(Employee)
```

Result

|Dept|
|----|
|IT|
|HR|

Duplicate IT removed.

---

## Why?

Because relations are Sets.

Sets cannot contain duplicates.

---

## Projection Formula

```
Input

↓

Choose Columns

↓

Remove Duplicate Rows

↓

Output
```

---

## Important Property

Projection

Changes columns.

May reduce rows if duplicates disappear.

---

## Memory Trick

Projection

↓

Project Screen

Only selected part is shown.

Columns are selected.

---

# Selection vs Projection

Most Asked Question

|Selection|Projection|
|----------|----------|
|Rows|Columns|
|σ|π|
|Condition Required|Attribute List Required|
|Columns Same|Columns Reduced|
|Rows Reduced|Duplicates May Reduce Rows|

---

Example

Employee

|ID|Name|Dept|
|--|----|----|
|1|Rahul|IT|
|2|Amit|HR|
|3|Neha|IT|

Selection

```
σ Dept='IT'
```

Returns

Rahul

Neha

Rows reduced.

---

Projection

```
π Name
```

Returns

Rahul

Amit

Neha

Columns reduced.

---

# 3. Rename Operator (ρ)

## Definition

Rename changes

- Relation Name
- Attribute Name
- Both

---

## Symbol

```
ρ
```

Pronounced

Rho

---

## Syntax

Rename Relation

```
ρ NewName(Relation)
```

Example

```
ρ Emp(Employee)
```

---

Rename Attributes

```
ρ(ID,EmployeeName,Salary)(Employee)
```

---

## Why Rename?

Suppose we join

Employee

with

Employee

(self join)

Both have

ID

Name

Salary

Confusion occurs.

Rename solves it.

---

Example

```
ρ E1(Employee)

ρ E2(Employee)
```

Now join becomes easier.

---

# 4. Union (∪)

Already studied in Chapter 3.

Quick revision.

---

Definition

Combine tuples from two relations.

---

Conditions

- Same Degree
- Compatible Domains

---

Example

R

|ID|
|--|
|1|
|2|

S

|ID|
|--|
|2|
|3|

Result

|ID|
|--|
|1|
|2|
|3|

Duplicate removed.

---

# 5. Difference (−)

Definition

Rows present in first relation but absent in second.

---

Example

R

|ID|
|--|
|1|
|2|
|3|

S

|ID|
|--|
|2|

Result

|ID|
|--|
|1|
|3|

---

Remember

```
R−S

≠

S−R
```

---

# 6. Cartesian Product (×)

Definition

Pairs every tuple of first relation with every tuple of second.

---

Example

Student

|ID|
|--|
|1|
|2|

Course

|Course|
|------|
|Java|
|Python|

Result

|ID|Course|
|--|------|
|1|Java|
|1|Python|
|2|Java|
|2|Python|

---

Formula

```
|R×S|

=

|R|

×

|S|
```

---

Example

R

5 tuples

S

8 tuples

Result

40 tuples

---

# Combining Operators

Most GATE questions combine operators.

Example

Employee

|ID|Name|Dept|Salary|
|--|----|----|------|
|1|Rahul|IT|50000|
|2|Amit|HR|40000|
|3|Neha|IT|70000|

Expression

```
π Name

(

σ Dept='IT'

(Employee)

)
```

Evaluation

Step 1

Selection

|ID|Name|Dept|Salary|
|--|----|----|------|
|1|Rahul|IT|50000|
|3|Neha|IT|70000|

Step 2

Projection

|Name|
|----|
|Rahul|
|Neha|

---

# Evaluation Rule

Always solve

Inside

↓

Outside

Like Mathematics.

Example

```
π Name

(

σ Salary>50000(Employee)

)
```

Step 1

Selection

↓

Step 2

Projection

---

# GATE-Level Example

Employee

|ID|Name|Dept|
|--|----|----|
|1|A|IT|
|2|B|HR|
|3|C|IT|

Expression

```
π Name

(

σ Dept='IT'

(Employee)

)
```

Answer

|Name|
|----|
|A|
|C|

---

# Common Mistakes

❌ Projection removes rows.

✔ Projection removes columns.

---

❌ Selection removes columns.

✔ Selection removes rows.

---

❌ Projection keeps duplicates.

✔ Projection removes duplicate tuples.

---

❌ Cartesian Product joins matching rows.

✔ It pairs **every** row with **every** row.

---

❌ Difference is commutative.

✔ It is **not**.

---

# Operator Summary

| Operator | Symbol | Removes | Output |
|-----------|--------|---------|--------|
|Selection|σ|Rows|Filtered Relation|
|Projection|π|Columns|Reduced Attributes|
|Rename|ρ|Nothing|New Name|
|Union|∪|Duplicates|Combined Relation|
|Difference|−|Matching Tuples|Remaining Tuples|
|Cartesian Product|×|Nothing|All Possible Pairs|

---

# IBPS SO Quick Notes

Remember these direct facts:

- σ → Row Filter
- π → Column Selection
- ρ → Rename
- ∪ → Combine Relations
- − → Remove Common Tuples
- × → Every Possible Pair
- Projection removes duplicate tuples.
- Selection never removes attributes.
- Union requires Union Compatibility.
- Cartesian Product does not.

---

# Memory Mnemonics

### σ (Selection)

**S = Select Rows**

---

### π (Projection)

**P = Pick Columns**

---

### ρ (Rename)

**R = Rename**

---

### ∪ (Union)

**U = Unite**

---

### − (Difference)

**D = Delete Second from First**

---

### × (Cartesian Product)

**C = Combine Every Pair**

---

# Practice Questions

### Q1

Which operator filters rows?

**Answer:** Selection (σ)

---

### Q2

Which operator removes duplicate tuples?

**Answer:** Projection (π) (when duplicate projected tuples arise)

---

### Q3

Which operator changes relation name?

**Answer:** Rename (ρ)

---

### Q4

If |R| = 7 and |S| = 9, then |R × S| = ?

**Answer:** 63

---

### Q5

Which operator requires a condition?

**Answer:** Selection

---

### Q6

Which operator requires an attribute list?

**Answer:** Projection

---

### Q7

Which operator is used before a self-join to avoid ambiguity?

**Answer:** Rename (ρ)

---

# Chapter Summary

- **Selection (σ)** filters rows based on conditions.
- **Projection (π)** selects columns and removes duplicate tuples.
- **Rename (ρ)** changes relation or attribute names.
- **Union (∪)** combines union-compatible relations.
- **Difference (−)** returns tuples in the first relation but not in the second.
- **Cartesian Product (×)** generates every possible tuple pair.
- Complex Relational Algebra expressions are evaluated from the innermost operation outward.
- Understanding these six primitive operators is essential before studying joins and division.

---

# Quick Revision Table

| Symbol | Name | Purpose |
|---------|------|---------|
| σ | Selection | Filter Rows |
| π | Projection | Select Columns |
| ρ | Rename | Rename Relation/Attributes |
| ∪ | Union | Combine Relations |
| − | Difference | Remove Matching Tuples |
| × | Cartesian Product | Every Possible Pair |

---

# Next Chapter

**Chapter 5: Derived Relational Algebra Operators**

Topics include:

- Join (⋈)
- Theta Join (⋈θ)
- Equi Join
- Natural Join
- Left Outer Join
- Right Outer Join
- Full Outer Join
- Semi Join
- Anti Join
- Division (÷)
- Intersection (∩)

These operators form the core of most **GATE** and advanced **IBPS SO IT Officer** Relational Algebra questions.

# Chapter 5: Derived Relational Algebra Operators
## Complete Notes for GATE CSE + IBPS SO IT Officer
### Join, Theta Join, Equi Join, Natural Join, Outer Join, Semi Join, Anti Join, Division & Intersection

---

# Chapter Overview

This is the **most important chapter** of Relational Algebra.

Almost **70–80% of GATE Relational Algebra questions** involve **Join** or **Division**.

IBPS SO IT Officer also asks conceptual questions about joins.

After studying this chapter, you will be able to solve questions like:

```
πA(R) − πA(R ⋈ S)

R ⋈ S

R ⋈A=B S

R ÷ S

Employee ⋈ Department
```

---

# 1. Why Do We Need JOIN?

Suppose we have two tables.

## Employee

| EmpID | Name | DeptID |
|------|------|--------|
|101|Rahul|10|
|102|Amit|20|
|103|Neha|10|

---

## Department

| DeptID | DeptName |
|--------|----------|
|10|IT|
|20|HR|

Question

> Find employee names along with department names.

Employee table has only DeptID.

Department table has DeptName.

We need to combine both tables.

This is done using **JOIN**.

---

# 2. JOIN Operator

## Symbol

```
⋈
```

Pronounced

> Join

---

## Definition

Join combines tuples from two relations based on a matching condition.

---

## General Syntax

```
R ⋈ Condition S
```

or

```
R ⋈ S
```

depending on join type.

---

# Types of Join

```
JOIN

│

├── Theta Join

├── Equi Join

├── Natural Join

├── Left Outer Join

├── Right Outer Join

├── Full Outer Join

├── Semi Join

└── Anti Join
```

---

# 3. Theta Join (⋈θ)

## Definition

Join using **any comparison operator**.

Allowed operators

```
=

≠

>

<

>=

<=
```

---

## Syntax

```
R ⋈ A>B S
```

Example

Employee

|ID|Salary|
|--|------|
|1|50000|
|2|60000|

Bonus

|Amount|
|------|
|45000|
|55000|

Query

```
Employee ⋈ Salary > Amount Bonus
```

Result

Every pair satisfying

```
Salary > Amount
```

---

## Important Point

Theta Join allows all comparison operators.

---

# 4. Equi Join

## Definition

A Theta Join that uses only

```
=
```

operator.

---

Example

Employee

|EmpID|DeptID|
|-----|------|
|101|10|
|102|20|

Department

|DeptID|DeptName|
|------|---------|
|10|IT|
|20|HR|

Query

```
Employee ⋈ Employee.DeptID = Department.DeptID Department
```

Result

|EmpID|DeptID|DeptID|DeptName|
|-----|------|------|---------|
|101|10|10|IT|
|102|20|20|HR|

Notice

Both DeptID columns remain.

---

### Exam Point

Equi Join keeps duplicate join columns.

---

# 5. Natural Join

Most Important.

---

## Definition

Natural Join automatically joins on attributes having

- Same Name
- Compatible Domain

Duplicate join columns are removed.

---

Example

Employee

|EmpID|Name|DeptID|
|-----|----|------|
|101|Rahul|10|
|102|Amit|20|

Department

|DeptID|DeptName|
|------|---------|
|10|IT|
|20|HR|

Natural Join

```
Employee ⋈ Department
```

Result

|EmpID|Name|DeptID|DeptName|
|-----|----|------|---------|
|101|Rahul|10|IT|
|102|Amit|20|HR|

Only one DeptID appears.

---

# Equi Join vs Natural Join

Most Asked Question

| Equi Join | Natural Join |
|------------|--------------|
|Condition written explicitly|Condition automatic|
|Duplicate columns remain|Duplicate columns removed|
|Uses = |Uses same-name attributes|

---

# Memory Trick

Equi Join

=

Equal

Keep duplicate columns.

Natural Join

=

Naturally remove duplicate columns.

---

# 6. Outer Join

Inner Join returns only matching rows.

Outer Join also keeps non-matching rows.

---

## Left Outer Join

Symbol

```
⟕
```

Keeps

All rows from Left Relation.

---

Employee

|EmpID|DeptID|
|-----|------|
|1|10|
|2|20|
|3|30|

Department

|DeptID|DeptName|
|------|---------|
|10|IT|
|20|HR|

Result

|EmpID|DeptID|DeptName|
|-----|------|---------|
|1|10|IT|
|2|20|HR|
|3|30|NULL|

Employee 3 is retained.

---

## Right Outer Join

Symbol

```
⟖
```

Keeps

All rows from Right Relation.

---

Department

|DeptID|DeptName|
|------|---------|
|10|IT|
|20|HR|
|30|Sales|

Employee

Only

10

20

Result

Sales appears with NULL employee.

---

## Full Outer Join

Symbol

```
⟗
```

Keeps

Everything.

Matching

+

Unmatched Left

+

Unmatched Right

---

# Outer Join Memory Trick

Left Outer Join

↓

Keep Left

---

Right Outer Join

↓

Keep Right

---

Full Outer Join

↓

Keep Both

---

# 7. Semi Join

Not frequently asked in IBPS.

Sometimes appears in GATE.

---

Definition

Returns only matching tuples from one relation.

Suppose

Employee

Department

Semi Join

Returns

Employee rows only

that have matching department.

Department columns are NOT included.

---

# 8. Anti Join

Returns tuples having

NO match.

Example

Employees

without Department.

Useful conceptually.

Equivalent to

```
Employee

−

(Employee ⋈ Department)
```

---

# 9. Intersection

Intersection is a derived operator.

Symbol

```
∩
```

---

Definition

Returns common tuples.

Formula

```
R ∩ S

=

R

−

(R−S)
```

Very important for GATE.

---

Example

R

```
1

2

3
```

S

```
2

3

4
```

Result

```
2

3
```

---

# 10. Division Operator

Most Difficult Operator.

Most Important for GATE.

---

## Symbol

```
÷
```

---

## Purpose

Find

"ALL"

type queries.

---

Example

Student

Course

|Student|Course|
|--------|------|
|A|Java|
|A|Python|
|B|Java|
|B|Python|
|C|Java|

Required Courses

|Course|
|------|
|Java|
|Python|

Question

Find students who completed

ALL required courses.

---

Expression

```
Completed

÷

RequiredCourses
```

Result

```
A

B
```

Not

C

Because

C completed only Java.

---

# Easy Trick

Whenever question contains

```
ALL

EVERY

EACH

COMPLETE SET
```

Think

Division Operator.

---

# Another Example

EmployeeSkill

|Employee|Skill|
|---------|-----|
|A|Java|
|A|SQL|
|B|Java|
|B|SQL|
|C|Java|

RequiredSkill

|Skill|
|-----|
|Java|
|SQL|

Division

Result

A

B

---

# 11. GATE Question Pattern

Suppose

R(A,B)

S(B)

Expression

```
R ÷ S
```

Output

Values of

A

associated with

every value of

B

present in S.

---

# 12. Join Evaluation

Suppose

Employee

|ID|Dept|
|--|----|
|1|10|
|2|20|

Department

|Dept|Name|
|----|----|
|10|IT|
|20|HR|

Natural Join

Step 1

Compare Dept.

↓

Step 2

Keep matching tuples.

↓

Step 3

Remove duplicate Dept column.

↓

Output.

---

# 13. Solving Expressions

Example

```
πA

(R)

−

πA

(R ⋈ S)
```

Very famous GATE pattern.

---

Step 1

```
πA(R)
```

All A values from R.

---

Step 2

```
R ⋈ S
```

Only matching tuples remain.

---

Step 3

```
πA(R⋈S)
```

A values having matching tuples.

---

Step 4

Subtract

Remaining A values

=

A values in R having

NO matching tuple in S.

---

### Interpretation Trick

Whenever you see

```
πA(R)

−

πA(R⋈S)
```

Think:

> Find A values from R that **do not participate in the join** with S.

This is one of the most frequently tested concepts in GATE.

---

# 14. Common Exam Tricks

### Trick 1

Natural Join

↓

Duplicate column removed.

---

### Trick 2

Equi Join

↓

Duplicate column kept.

---

### Trick 3

Theta Join

↓

Any comparison operator.

---

### Trick 4

Division

↓

ALL

EVERY

FOR ALL

---

### Trick 5

Outer Join

↓

Keeps unmatched tuples.

---

# 15. GATE Practice Questions

### Q1

Natural Join removes

A. Rows

B. Duplicate Attributes

C. Duplicate Tuples

D. NULL

Answer

B

---

### Q2

Theta Join can use

```
>
```

Answer

Yes

---

### Q3

Which Join automatically matches common attributes?

Answer

Natural Join

---

### Q4

Division operator answers

A.

Exists

B.

All

C.

Maximum

D.

Minimum

Answer

B

---

### Q5

Expression

```
πA(R)

−

πA(R⋈S)
```

represents

Answer

Values of A in R having no matching tuple in S.

---

### Q6

Which Join keeps unmatched left tuples?

Answer

Left Outer Join

---

### Q7

Which Join keeps duplicate join columns?

Answer

Equi Join

---

# 16. IBPS SO Quick Revision

- Join combines relations.
- Theta Join uses any comparison operator.
- Equi Join uses '='.
- Natural Join automatically joins common attributes.
- Natural Join removes duplicate join columns.
- Left Outer Join keeps all left tuples.
- Right Outer Join keeps all right tuples.
- Full Outer Join keeps everything.
- Semi Join returns matching tuples from one relation only.
- Anti Join returns non-matching tuples.
- Division answers "ALL" type queries.
- Intersection returns common tuples.

---

# 17. Memory Mnemonics

### Theta Join

**T = Test with any operator**

---

### Equi Join

**E = Equal (=)**

---

### Natural Join

**N = No duplicate join column**

---

### Division

Think

```
ALL

EVERY

FOR ALL

COMPLETE
```

---

### Outer Join

```
Left

↓

Keep Left

Right

↓

Keep Right

Full

↓

Keep Both
```

---

# 18. Comparison Table

| Operator | Symbol | Purpose |
|-----------|--------|---------|
| Theta Join | ⋈θ | Join using any comparison |
| Equi Join | ⋈ | Join using = |
| Natural Join | ⋈ | Automatic join on common attributes |
| Left Outer Join | ⟕ | Keep all left tuples |
| Right Outer Join | ⟖ | Keep all right tuples |
| Full Outer Join | ⟗ | Keep all tuples |
| Semi Join | ⋉ / ⋊ | Return matching tuples from one side |
| Anti Join | — | Return non-matching tuples |
| Intersection | ∩ | Common tuples |
| Division | ÷ | "For all" queries |

---

# Chapter Summary

- Join combines related tuples from two relations.
- Theta Join allows any comparison operator.
- Equi Join is a Theta Join using only '='.
- Natural Join automatically joins on common attributes and removes duplicate join columns.
- Outer Joins preserve unmatched tuples.
- Semi Join returns matching tuples from one relation.
- Anti Join returns non-matching tuples.
- Intersection is a derived operator.
- Division is used for "ALL" type queries.
- The expression `πA(R) − πA(R ⋈ S)` returns values of **A** in **R** that have **no matching tuple in S**.

---

# Quick Revision (1 Minute)

| Question | Answer |
|----------|--------|
| Join Symbol | ⋈ |
| Theta Join | Any comparison operator |
| Equi Join | '=' only |
| Natural Join | Removes duplicate join columns |
| Left Outer Join | Keeps all left tuples |
| Right Outer Join | Keeps all right tuples |
| Full Outer Join | Keeps all tuples |
| Division Symbol | ÷ |
| Division Used For | ALL / EVERY queries |
| Expression `πA(R) − πA(R⋈S)` | A values in R with no matching tuple in S |
| Most Important Operator for GATE | Join & Division |

---

# What's Next?

## Chapter 6: Solving Relational Algebra Questions Like GATE

This chapter will focus entirely on problem-solving:

- Step-by-step evaluation of RA expressions
- Nested expressions
- Complex joins
- Division problems
- Previous GATE-style questions
- Shortcuts and elimination techniques
- 50+ fully solved exam-level questions


# Chapter 6: How to Solve Relational Algebra Questions Like GATE & IBPS SO IT Officer
## Complete Problem-Solving Guide
### Step-by-Step Evaluation, Tricks, Previous-Year Patterns & Solved Examples

---

# Chapter Overview

Until now, you have learned:

- Relation
- Tuple
- Attribute
- Schema
- Set Theory
- Selection
- Projection
- Union
- Difference
- Cartesian Product
- Join
- Division

Now comes the most important part:

> **How to solve Relational Algebra questions in the exam.**

Many students know the operators but still fail because they evaluate expressions incorrectly.

This chapter teaches the **thinking process** used by GATE toppers.

---

# 1. Golden Rule of Relational Algebra

## Never solve the entire expression at once.

Always break it into small steps.

Think like mathematics.

Example

```
(5 + 2) × 10
```

We first solve

```
5 + 2
```

Then

```
7 × 10
```

Exactly the same rule applies in Relational Algebra.

---

# 2. Evaluation Order

Always solve

```
Innermost Expression

↓

Selection

↓

Projection

↓

Join

↓

Set Operations

↓

Final Answer
```

---

## Example

```
π Name

(

σ Salary > 50000

(Employee)

)
```

Step 1

Selection

↓

Step 2

Projection

---

# 3. The Five-Step Method

This is the easiest way to solve almost every RA question.

### Step 1

Write the given relation.

---

### Step 2

Mark the operator.

---

### Step 3

Perform one operator at a time.

---

### Step 4

Write the intermediate relation.

---

### Step 5

Repeat until finished.

---

# Example 1

Employee

|ID|Name|Salary|
|--|----|------|
|1|Rahul|40000|
|2|Amit|70000|
|3|Neha|60000|

Expression

```
π Name

(

σ Salary > 50000(Employee)

)
```

---

## Step 1

Selection

Salary > 50000

Result

|ID|Name|Salary|
|--|----|------|
|2|Amit|70000|
|3|Neha|60000|

---

## Step 2

Projection

Name

Result

|Name|
|----|
|Amit|
|Neha|

Final Answer

```
Amit

Neha
```

---

# 4. Solving Join Questions

Employee

|EmpID|DeptID|
|-----|------|
|1|10|
|2|20|

Department

|DeptID|DeptName|
|------|--------|
|10|IT|
|20|HR|

Expression

```
Employee ⋈ Department
```

---

## Step 1

Compare DeptID.

---

## Step 2

Match values.

---

## Step 3

Merge rows.

---

Result

|EmpID|DeptID|DeptName|
|-----|------|--------|
|1|10|IT|
|2|20|HR|

---

# 5. Solving Projection After Join

Expression

```
π DeptName

(

Employee ⋈ Department

)
```

---

Step 1

Join

↓

|EmpID|DeptID|DeptName|
|-----|------|--------|
|1|10|IT|
|2|20|HR|

---

Step 2

Projection

↓

|DeptName|
|--------|
|IT|
|HR|

---

# 6. Solving Nested Expressions

Example

```
π Name

(

σ Dept='IT'

(

Employee

)

)
```

---

Rule

Always start from inside.

Employee

↓

Selection

↓

Projection

---

Never start from Projection.

---

# 7. Understanding This Famous GATE Expression

One of the most frequently asked patterns:

```
πA(R)

−

πA(R ⋈ S)
```

---

Suppose

### Relation R(A,B)

|A|B|
|--|--|
|1|10|
|2|20|
|3|30|
|4|40|

---

### Relation S(B,C)

|B|C|
|--|--|
|20|X|
|30|Y|

---

Question

Find

```
πA(R)

−

πA(R⋈S)
```

---

## Step 1

Projection on R

```
πA(R)
```

Result

|A|
|--|
|1|
|2|
|3|
|4|

---

## Step 2

Natural Join

Common attribute

B

Matching tuples

|A|B|C|
|--|--|--|
|2|20|X|
|3|30|Y|

---

## Step 3

Projection

```
πA(R⋈S)
```

Result

|A|
|--|
|2|
|3|

---

## Step 4

Difference

```
{1,2,3,4}

−

{2,3}
```

Answer

|A|
|--|
|1|
|4|

---

## Interpretation

These are the A values whose B values **did not find a match in S**.

---

### Shortcut

Whenever you see

```
πA(R)

−

πA(R⋈S)
```

Think immediately:

> **Rows in R that do not participate in the join with S.**

This shortcut saves a lot of time in GATE.

---

# 8. Solving Cartesian Product Questions

R

|A|
|--|
|1|
|2|

S

|B|
|--|
|X|
|Y|
|Z|

---

Question

```
R × S
```

---

Rule

Pair every row with every row.

Result

|A|B|
|--|--|
|1|X|
|1|Y|
|1|Z|
|2|X|
|2|Y|
|2|Z|

Rows

```
2 × 3

=

6
```

---

# 9. Solving Division Questions

EmployeeSkill

|Emp|Skill|
|---|-----|
|A|Java|
|A|SQL|
|B|Java|
|B|SQL|
|C|Java|

RequiredSkill

|Skill|
|-----|
|Java|
|SQL|

Expression

```
EmployeeSkill

÷

RequiredSkill
```

---

Question

Who has **ALL** required skills?

---

Check each employee

A

Java ✔

SQL ✔

Selected

---

B

Java ✔

SQL ✔

Selected

---

C

Java ✔

SQL ✘

Rejected

---

Answer

```
A

B
```

---

# 10. GATE Shortcuts

## Shortcut 1

Selection

↓

Rows

---

## Shortcut 2

Projection

↓

Columns

---

## Shortcut 3

Natural Join

↓

Match common columns

↓

Remove duplicate column

---

## Shortcut 4

Cartesian Product

↓

Multiply rows

---

## Shortcut 5

Division

↓

Think

ALL

EVERY

FOR ALL

---

# 11. Common GATE Patterns

### Pattern 1

Selection followed by Projection

```
π

(

σ

)
```

Very common.

---

### Pattern 2

Join followed by Projection

```
π

(

R⋈S

)
```

---

### Pattern 3

Projection after Difference

---

### Pattern 4

Nested Joins

---

### Pattern 5

Division

---

# 12. Common Mistakes

❌ Starting from left to right.

✔ Always solve the innermost expression first.

---

❌ Forgetting duplicate removal after Projection.

✔ Projection eliminates duplicate tuples.

---

❌ Forgetting duplicate join column removal in Natural Join.

✔ Natural Join keeps only one copy of the common attribute.

---

❌ Confusing Degree with Cardinality.

✔ Degree = Columns

✔ Cardinality = Rows

---

❌ Thinking Difference is commutative.

✔

```
R − S

≠

S − R
```

---

# 13. Fully Solved GATE-Style Questions

---

## Question 1

Employee

|ID|Dept|
|--|----|
|1|IT|
|2|HR|
|3|IT|

Find

```
σ Dept='IT'
```

Answer

|ID|Dept|
|--|----|
|1|IT|
|3|IT|

---

## Question 2

Employee

|ID|Name|Dept|
|--|----|----|
|1|A|IT|
|2|B|HR|

Find

```
π Name
```

Answer

|Name|
|----|
|A|
|B|

---

## Question 3

If

```
|R|=8

|S|=6
```

Find

```
|R×S|
```

Answer

```
48
```

---

## Question 4

Natural Join removes

A. Rows

B. Duplicate tuples

C. Duplicate join columns

D. NULL

Answer

C

---

## Question 5

Division answers which type of query?

A.

Exists

B.

At least one

C.

For all

D.

Maximum

Answer

C

---

## Question 6

Projection operates on

A. Rows

B. Columns

C. Both

D. Neither

Answer

B

---

## Question 7

Selection operates on

A. Rows

B. Columns

Answer

A

---

## Question 8

Which operator requires union compatibility?

A. Join

B. Cartesian Product

C. Union

D. Projection

Answer

C

---

## Question 9

What is the result of:

```
πA(R)

−

πA(R⋈S)
```

Answer

Values of A in R whose tuples do **not** join with S.

---

## Question 10

Natural Join is based on

A.

Common attribute names and compatible domains

B.

Primary keys only

C.

Foreign keys only

D.

Tuple numbers

Answer

A

---

# 14. How IBPS SO Asks RA Questions

Mostly conceptual.

Examples

- Which operator selects rows?
- Which operator selects columns?
- Which join removes duplicate columns?
- Difference between Equi Join and Natural Join?
- Meaning of Division?
- Closure Property?
- Degree vs Cardinality?

Usually no lengthy calculations.

---

# 15. Last-Minute Revision Table

| Operator | Think |
|----------|-------|
|σ|Rows|
|π|Columns|
|ρ|Rename|
|∪|Combine|
|−|Subtract|
|×|Multiply rows|
|⋈|Match rows|
|÷|ALL / EVERY|

---

# 16. One-Minute Memory Tricks

### Sigma (σ)

**S = Select Rows**

---

### Pi (π)

**P = Pick Columns**

---

### Join

**J = Join Matching Rows**

---

### Division

Think

```
ALL

EVERY

COMPLETE
```

---

### Cartesian Product

Think

```
Every

×

Every
```

---

# Chapter Summary

- Solve Relational Algebra expressions from the innermost operation outward.
- Break complex expressions into intermediate relations.
- Selection filters rows; Projection selects columns.
- Natural Join matches common attributes and removes duplicate join columns.
- Cartesian Product creates every possible pair of tuples.
- Division is used for "for all" queries.
- The expression `πA(R) − πA(R ⋈ S)` identifies A-values from R that have **no matching tuple in S**.
- GATE focuses on step-by-step evaluation, while IBPS SO emphasizes conceptual understanding.

---

# Complete Relational Algebra Problem-Solving Checklist

Before answering any RA question, ask yourself:

- ✅ Which operator is applied first?
- ✅ Does Projection remove duplicates?
- ✅ Does Natural Join remove duplicate join columns?
- ✅ Is Union Compatibility required?
- ✅ Is the expression asking for unmatched tuples?
- ✅ Does the word **ALL** indicate Division?
- ✅ Have I counted rows (cardinality) and columns (degree) correctly?
- ✅ Did I evaluate the expression from inside to outside?

If you can answer all of these correctly, you'll be able to solve the vast majority of **GATE** and **IBPS SO IT Officer** Relational Algebra questions confidently.

---

# What's Next?

## Chapter 7: SQL and Relational Algebra Mapping

You'll learn:

- How every SQL query translates into Relational Algebra
- SELECT, WHERE, FROM, JOIN, GROUP BY, HAVING in RA
- GATE conversion questions (SQL ↔ RA)
- IBPS SO conceptual questions
- 40+ solved conversion examples

# Chapter 7: SQL and Relational Algebra Mapping
## Complete Notes for GATE CSE + IBPS SO IT Officer
### SQL ↔ Relational Algebra Conversion Guide

---

# Chapter Overview

This is one of the most important chapters because **SQL is based on Relational Algebra**.

In GATE, many questions ask:

- Convert SQL into Relational Algebra.
- Convert Relational Algebra into SQL.
- Find the equivalent SQL query.
- Find the equivalent Relational Algebra expression.

IBPS SO usually asks conceptual questions like:

- SQL is based on which mathematical language?
- Which SQL clause corresponds to Selection?
- Which SQL clause corresponds to Projection?

---

# Learning Outcomes

After completing this chapter, you will be able to:

- Convert SQL to Relational Algebra
- Convert Relational Algebra to SQL
- Understand SQL execution using RA
- Solve GATE conversion questions
- Solve IBPS conceptual questions

---

# 1. SQL vs Relational Algebra

| SQL | Relational Algebra |
|------|--------------------|
| Declarative | Procedural |
| User writes queries | DBMS internally uses it |
| Commercial language | Mathematical language |
| Uses English keywords | Uses symbols |
| Practical | Theoretical |

---

# 2. SQL Processing Inside DBMS

Whenever we write

```sql
SELECT Name
FROM Employee
WHERE Salary > 50000;
```

Database internally performs

```
SQL Query

↓

Parser

↓

Relational Algebra

↓

Query Optimizer

↓

Execution Plan

↓

Output
```

Remember

> SQL is translated into Relational Algebra before execution.

---

# 3. Mapping Between SQL and Relational Algebra

| SQL Clause | Relational Algebra |
|------------|--------------------|
| SELECT columns | Projection (π) |
| WHERE | Selection (σ) |
| FROM | Relation |
| JOIN | Join (⋈) |
| UNION | Union (∪) |
| INTERSECT | Intersection (∩) |
| EXCEPT/MINUS | Difference (−) |
| CROSS JOIN | Cartesian Product (×) |
| RENAME (Alias) | Rename (ρ) |

This table is extremely important.

---

# 4. SQL SELECT → Projection

SQL

```sql
SELECT Name
FROM Employee;
```

Relational Algebra

```
π Name(Employee)
```

Explanation

Projection chooses columns.

---

Example

Employee

|ID|Name|Dept|
|--|----|----|
|1|Rahul|IT|
|2|Amit|HR|

Output

|Name|
|----|
|Rahul|
|Amit|

---

# 5. SQL WHERE → Selection

SQL

```sql
SELECT *
FROM Employee
WHERE Salary > 50000;
```

Relational Algebra

```
σ Salary>50000(Employee)
```

Selection filters rows.

---

# 6. SELECT + WHERE

Most Common Conversion

SQL

```sql
SELECT Name
FROM Employee
WHERE Salary > 50000;
```

Relational Algebra

```
π Name

(

σ Salary>50000(Employee)

)
```

Evaluation

Step 1

Selection

↓

Step 2

Projection

---

# 7. Multiple Conditions

SQL

```sql
SELECT Name
FROM Employee
WHERE Dept='IT'
AND Salary>50000;
```

Relational Algebra

```
π Name

(

σ Dept='IT'

AND

Salary>50000

(Employee)

)
```

---

# 8. OR Condition

SQL

```sql
SELECT *
FROM Employee
WHERE Dept='IT'
OR Dept='HR';
```

Relational Algebra

```
σ Dept='IT'

OR

Dept='HR'

(Employee)
```

---

# 9. NOT Condition

SQL

```sql
SELECT *
FROM Employee
WHERE NOT Dept='IT';
```

Relational Algebra

```
σ NOT Dept='IT'

(Employee)
```

---

# 10. JOIN Conversion

Employee

|EmpID|DeptID|
|-----|------|
|101|10|
|102|20|

Department

|DeptID|DeptName|
|------|--------|
|10|IT|
|20|HR|

---

SQL

```sql
SELECT *
FROM Employee
JOIN Department
ON Employee.DeptID = Department.DeptID;
```

Relational Algebra

```
Employee

⋈

Employee.DeptID

=

Department.DeptID

Department
```

---

# 11. Natural Join

SQL

```sql
SELECT *
FROM Employee
NATURAL JOIN Department;
```

Relational Algebra

```
Employee

⋈

Department
```

Natural Join automatically joins common attributes.

---

# 12. Projection After Join

SQL

```sql
SELECT Name,DeptName
FROM Employee
JOIN Department
ON Employee.DeptID=Department.DeptID;
```

Relational Algebra

```
π Name,

DeptName

(

Employee

⋈

Department

)
```

---

# 13. SQL UNION

Employee2024

Employee2025

SQL

```sql
SELECT ID
FROM Employee2024

UNION

SELECT ID
FROM Employee2025;
```

Relational Algebra

```
π ID(Employee2024)

∪

π ID(Employee2025)
```

---

# 14. SQL INTERSECT

SQL

```sql
SELECT ID
FROM A

INTERSECT

SELECT ID
FROM B;
```

Relational Algebra

```
π ID(A)

∩

π ID(B)
```

---

# 15. SQL EXCEPT / MINUS

SQL

```sql
SELECT ID
FROM A

EXCEPT

SELECT ID
FROM B;
```

Relational Algebra

```
π ID(A)

−

π ID(B)
```

---

# 16. SQL CROSS JOIN

SQL

```sql
SELECT *
FROM A
CROSS JOIN B;
```

Relational Algebra

```
A × B
```

---

# 17. SQL Alias → Rename

SQL

```sql
SELECT *
FROM Employee E;
```

Relational Algebra

```
ρ E(Employee)
```

---

# 18. SQL DISTINCT

SQL

```sql
SELECT DISTINCT Dept
FROM Employee;
```

Relational Algebra

```
π Dept(Employee)
```

Reason

Projection automatically removes duplicate tuples.

---

# 19. SQL IN

SQL

```sql
SELECT *
FROM Employee
WHERE Dept IN ('IT','HR');
```

Equivalent

```
Dept='IT'

OR

Dept='HR'
```

Relational Algebra

```
σ Dept='IT'

OR

Dept='HR'

(Employee)
```

---

# 20. SQL BETWEEN

SQL

```sql
SELECT *
FROM Employee
WHERE Salary BETWEEN 50000 AND 70000;
```

Equivalent

```
Salary>=50000

AND

Salary<=70000
```

Relational Algebra

```
σ Salary>=50000

AND

Salary<=70000

(Employee)
```

---

# 21. SQL LIKE

Standard Relational Algebra does not directly support pattern matching.

Example

```sql
WHERE Name LIKE 'A%'
```

This is an SQL-specific feature.

---

# 22. Aggregate Functions

SQL

```sql
SELECT COUNT(*)
FROM Employee;
```

Standard/basic Relational Algebra does **not** support aggregates.

Extended Relational Algebra introduces

- γ (Gamma)

for grouping and aggregation.

For IBPS SO, remember:

Basic RA → No COUNT(), SUM(), AVG()

---

# 23. GROUP BY

SQL

```sql
SELECT Dept,
COUNT(*)
FROM Employee
GROUP BY Dept;
```

Extended Relational Algebra

```
γ Dept,

COUNT(*)

(Employee)
```

---

# 24. HAVING

SQL

```sql
SELECT Dept
FROM Employee
GROUP BY Dept
HAVING COUNT(*)>5;
```

Extended RA

```
σ COUNT>5

(

γ Dept,

COUNT(*)

(Employee)

)
```

Mostly asked in advanced GATE questions.

---

# 25. ORDER BY

SQL

```sql
ORDER BY Salary;
```

Standard Relational Algebra

Not Supported.

Reason

Relations are unordered.

---

# 26. INSERT, UPDATE, DELETE

These are SQL Data Manipulation Language (DML) commands.

Relational Algebra only retrieves data.

Therefore

No equivalent basic RA operator.

---

# 27. Complete SQL to RA Examples

---

## Example 1

SQL

```sql
SELECT Name
FROM Employee;
```

RA

```
π Name(Employee)
```

---

## Example 2

SQL

```sql
SELECT *
FROM Employee
WHERE Dept='IT';
```

RA

```
σ Dept='IT'(Employee)
```

---

## Example 3

SQL

```sql
SELECT Name
FROM Employee
WHERE Salary>50000;
```

RA

```
π Name

(

σ Salary>50000(Employee)

)
```

---

## Example 4

SQL

```sql
SELECT *
FROM Employee
JOIN Department
ON Employee.DeptID=Department.DeptID;
```

RA

```
Employee

⋈

Employee.DeptID

=

Department.DeptID

Department
```

---

## Example 5

SQL

```sql
SELECT ID
FROM A

UNION

SELECT ID
FROM B;
```

RA

```
π ID(A)

∪

π ID(B)
```

---

# 28. Complete RA to SQL Examples

---

RA

```
π Name(Employee)
```

SQL

```sql
SELECT Name
FROM Employee;
```

---

RA

```
σ Salary>50000(Employee)
```

SQL

```sql
SELECT *
FROM Employee
WHERE Salary>50000;
```

---

RA

```
π Name

(

σ Dept='IT'

(Employee)

)
```

SQL

```sql
SELECT Name
FROM Employee
WHERE Dept='IT';
```

---

RA

```
Employee ⋈ Department
```

SQL

```sql
SELECT *
FROM Employee
NATURAL JOIN Department;
```

---

# 29. GATE-Level Conversion Question

Given

```
π Name

(

σ Salary>50000

(Employee)

)
```

Equivalent SQL

```sql
SELECT Name
FROM Employee
WHERE Salary>50000;
```

---

# 30. IBPS SO Direct Questions

### Q1

Projection corresponds to

A.

WHERE

B.

SELECT

C.

FROM

D.

JOIN

Answer

B

---

### Q2

Selection corresponds to

A.

WHERE

B.

FROM

C.

GROUP BY

D.

ORDER BY

Answer

A

---

### Q3

Which SQL clause has no direct equivalent in standard Relational Algebra?

A.

SELECT

B.

WHERE

C.

ORDER BY

D.

JOIN

Answer

C

---

### Q4

Which SQL feature requires Extended Relational Algebra?

A.

Projection

B.

Selection

C.

COUNT()

D.

Join

Answer

C

---

# 31. Common GATE Tricks

### Trick 1

SELECT

↓

Projection

---

### Trick 2

WHERE

↓

Selection

---

### Trick 3

JOIN

↓

Join

---

### Trick 4

UNION

↓

Union

---

### Trick 5

EXCEPT

↓

Difference

---

### Trick 6

CROSS JOIN

↓

Cartesian Product

---

### Trick 7

DISTINCT

↓

Already handled by Projection.

---

# 32. Common Mistakes

❌ Thinking SELECT corresponds to Selection.

✔ SELECT corresponds to Projection because it chooses columns.

---

❌ Thinking WHERE corresponds to Projection.

✔ WHERE corresponds to Selection because it filters rows.

---

❌ Thinking ORDER BY exists in RA.

✔ Relations are unordered.

---

❌ Thinking COUNT() exists in standard RA.

✔ Aggregation belongs to Extended RA.

---

# 33. SQL ↔ RA Cheat Sheet

| SQL | Relational Algebra |
|------|--------------------|
| SELECT | π |
| WHERE | σ |
| JOIN | ⋈ |
| NATURAL JOIN | ⋈ |
| UNION | ∪ |
| INTERSECT | ∩ |
| EXCEPT / MINUS | − |
| CROSS JOIN | × |
| Alias | ρ |
| DISTINCT | π (duplicates removed automatically) |
| GROUP BY | γ (Extended RA) |
| HAVING | σ after γ |
| ORDER BY | Not Supported |
| COUNT(), SUM(), AVG() | γ (Extended RA) |

---

# 34. Memory Mnemonics

### SELECT

Think

**Select Columns**

↓

Projection (π)

---

### WHERE

Think

**Where Condition**

↓

Selection (σ)

---

### JOIN

Think

**Join Tables**

↓

⋈

---

### GROUP BY

Think

**Group**

↓

Gamma (γ)

---

# Chapter Summary

- SQL is a declarative language, while Relational Algebra is procedural.
- SQL queries are internally converted into Relational Algebra by the DBMS.
- `SELECT` maps to **Projection (π)**.
- `WHERE` maps to **Selection (σ)**.
- `JOIN` maps to **Join (⋈)**.
- `UNION`, `INTERSECT`, `EXCEPT`, and `CROSS JOIN` map directly to their corresponding RA operators.
- `DISTINCT` is naturally handled by Projection because RA relations do not contain duplicate tuples.
- `GROUP BY` and aggregate functions belong to **Extended Relational Algebra** using the **Gamma (γ)** operator.
- `ORDER BY` has no equivalent in standard Relational Algebra because relations are unordered.

---

# One-Page Revision

| Remember | Answer |
|-----------|--------|
| SELECT | π |
| WHERE | σ |
| JOIN | ⋈ |
| UNION | ∪ |
| EXCEPT | − |
| INTERSECT | ∩ |
| CROSS JOIN | × |
| Alias | ρ |
| GROUP BY | γ |
| ORDER BY | Not in Standard RA |
| COUNT() | Extended RA |
| SQL Type | Declarative |
| RA Type | Procedural |

---

# What's Next?

## Chapter 8: GATE & IBPS SO Previous-Year Style Relational Algebra Questions 

This chapter will include:
- Real GATE-level pattern questions
- IBPS SO conceptual MCQs
- Expression evaluation
- Join and Division problems
- Step-by-step solutions
- Shortcuts and elimination techniques

