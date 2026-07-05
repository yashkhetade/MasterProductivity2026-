# DBMS Notes
# Lossy vs Lossless Decomposition 


---

# Table of Contents

1. Introduction
2. What is Decomposition?
3. Why Do We Need Decomposition?
4. Everyday Life Analogy
5. Good Decomposition vs Bad Decomposition
6. What is Lossless Decomposition?
7. What is Lossy Decomposition?
8. Step-by-Step Examples
9. Comparison Table
10. Memory Tricks
11. Important Exam Points

---

# Introduction

One of the most important topics in **Normalization** is **Decomposition**.

Almost every university, GATE, NIELIT, and IBPS SO exam asks questions on:

- Lossless Decomposition
- Lossy Decomposition
- Functional Dependency
- Normal Forms

Students usually memorize definitions but fail to understand **why decomposition is needed**.

Once you understand the idea, you will never forget it.

---

# Imagine This...

Suppose you maintain one large table.

| StudentID | StudentName | Course | Faculty | FacultyRoom |
|-----------|-------------|---------|----------|-------------|
|101|Rahul|DBMS|Sharma|A101|
|102|Amit|OS|Verma|B202|
|103|Rahul|Java|Sharma|A101|

Looks okay?

Now imagine 50,000 students.

Problems arise:

- Duplicate faculty names
- Duplicate rooms
- Updating room everywhere
- Wasted storage
- More chances of mistakes

This is why we normalize.

---

# What is Decomposition?

## Definition

Decomposition means

> Breaking one large relation (table) into two or more smaller relations without losing important information.

Think of it as:

```
Large Table

↓

Smaller Tables
```

Example

Instead of

Student

|Roll|Name|Department|Department Head|

Create

Student

|Roll|Name|Department|

Department

|Department|Department Head|

Same information.

Less repetition.

Cleaner database.

---

# Simple Definition for Exams

> Decomposition is the process of dividing a relation into smaller relations to reduce redundancy and improve database design.

---

# Why Do We Need Decomposition?

Suppose this table exists.

Employee

|EmpID|EmpName|Department|Department Phone|

|101|Amit|IT|1111|

|102|Rahul|IT|1111|

|103|Riya|HR|2222|

Notice

Department Phone repeats.

If IT phone changes

1111

to

9999

You must update EVERY IT employee.

If you forget one row

Database becomes inconsistent.

This is called

**Update Anomaly**

---

Similarly

Deletion anomaly

Insert anomaly

also happen.

To remove these problems

we decompose tables.

---

# Everyday Analogy

Imagine your school notebook.

Instead of writing

Rahul
Class 10
School ABC
Principal Mr Sharma

100 times

You write

Student Notebook

|Student|Class|

School Notebook

|School|Principal|

Cleaner

Smaller

No repetition

Exactly same idea.

---

# Decomposition Should Preserve Information

Breaking a table is good.

But...

Breaking incorrectly is dangerous.

Suppose

Original Table

|Student|Course|

Rahul DBMS

Amit Java

Now divide into

Table1

|Student|

Rahul

Amit

Table2

|Course|

DBMS

Java

Can we reconstruct original table?

No.

Because

Rahul may study Java.

Amit may study DBMS.

We don't know.

Information is lost.

This is bad decomposition.

---

# Two Types of Decomposition

```
             Decomposition

              /          \

     Lossless           Lossy
```

---

# What is Lossless Decomposition?

## Simple Definition

Lossless means

**No information is lost after decomposition.**

We can always reconstruct the original table exactly.

No extra rows.

No missing rows.

Exactly same table.

---

Think

Original Table

↓

Split

↓

Join Again

↓

Original Table Back

Exactly Same

---

Formula

```
Original Table

↓

Decompose

↓

Join

↓

Original Table
```

If this happens

Lossless Decomposition

---

# Simple Example

Original Table

Employee

|EmpID|Name|Department|

101 Amit IT

102 Rahul HR

Split into

Employee

|EmpID|Name|

101 Amit

102 Rahul

Department

|EmpID|Department|

101 IT

102 HR

Now Join

EmpID matches

Result

|EmpID|Name|Department|

101 Amit IT

102 Rahul HR

Exactly same.

Nothing lost.

Hence

Lossless.

---

# Why is it Called Lossless?

Because

Nothing is lost.

```
Original Information

↓

Split

↓

Join

↓

Everything Returned
```

---

# Properties of Lossless Decomposition

✔ Original table recovered

✔ No fake rows

✔ No information loss

✔ Preferred in normalization

✔ Database remains correct

---

# Example 2

Original Relation

Student

|Roll|Name|Branch|

1 Rahul CS

2 Amit IT

Split

StudentInfo

|Roll|Name|

1 Rahul

2 Amit

BranchInfo

|Roll|Branch|

1 CS

2 IT

Join using Roll

Result

Exactly original.

Lossless.

---

# What is Lossy Decomposition?

Now suppose

Original Table

|Student|Course|

Rahul DBMS

Amit Java

Split

Students

Rahul

Amit

Courses

DBMS

Java

Join

Every student combines with every course.

Result

Rahul DBMS

Rahul Java

Amit DBMS

Amit Java

Original had only

Rahul DBMS

Amit Java

Now

Extra rows appeared.

Information changed.

This is

Lossy Decomposition.

---

# Simple Definition

Lossy decomposition means

Information cannot be recovered exactly after decomposition.

Extra tuples appear

or

Some original tuples disappear.

---

# Why is Lossy Dangerous?

Because database becomes wrong.

Example

Original

Rahul studies DBMS

Amit studies Java

After joining

Database says

Rahul studies Java

which is false.

---

# Properties of Lossy Decomposition

❌ Information lost

❌ Extra tuples generated

❌ Wrong answers

❌ Incorrect query results

❌ Never preferred

---

# Visual Understanding

Lossless

```
Original

ABC

↓

Split

↓

Join

↓

ABC
```

Lossy

```
Original

ABC

↓

Split

↓

Join

↓

ABCDXYZ
```

Extra information generated.

Wrong.

---

# Real-Life Analogy

Imagine cutting a photograph.

Suppose photo has

Mother

Father

Child

You cut into two halves carefully.

Later

Join.

Complete photo returns.

Lossless.

---

Now

Suppose

Pieces get mixed with another photo.

After joining

Mother

Father

Unknown Child

Wrong photo.

Lossy.

---

# Restaurant Analogy

Original Bill

|Table|Customer|Food|

1 Rahul Pizza

2 Amit Burger

Split

Customer Table

Rahul

Amit

Food Table

Pizza

Burger

Join

Now

Rahul Pizza

Rahul Burger

Amit Pizza

Amit Burger

Restaurant records become wrong.

Lossy.

---

# Train Reservation Analogy

Original

Passenger

Seat

Rahul S1

Amit S2

Split

Passengers

Rahul

Amit

Seats

S1

S2

Join

Rahul S2

Amit S1

Wrong reservation.

Lossy decomposition.

---

# School Example

Original

|Roll|Subject|

1 Math

2 Science

Split

Roll Table

1

2

Subject Table

Math

Science

Join

1 Math

1 Science

2 Math

2 Science

Wrong.

Lossy.

---

# Comparison

|Feature|Lossless|Lossy|
|--------|---------|------|
|Information Lost?|No|Yes|
|Original Table Recover?|Yes|No|
|Extra Tuples?|No|Yes|
|Preferred?|Yes|No|
|Normalization?|Used|Avoided|
|Database Correct?|Yes|No|

---

# Easy Memory Trick

Remember

```
LossLESS

LESS Loss

No Information Lost
```

---

Remember

```
LossY

WHY?

Why did information disappear?
```

---

# Another Memory Trick

Imagine

Glass of Water

Pour into two glasses.

Pour back.

Still same quantity.

Lossless.

---

Now

One glass leaks.

Pour back.

Water missing.

Lossy.

---

# Golden Rule

Whenever you decompose a relation, ask only one question:

> **Can I reconstruct the original table exactly by joining the decomposed tables?**

- **Yes → Lossless**
- **No → Lossy**

This single question solves most conceptual exam questions.

---

# Important Points for Exams

### Lossless

- No information loss
- Original relation recovered exactly
- No spurious (fake) tuples
- Always desirable
- Used during normalization

---

### Lossy

- Information lost
- Original relation cannot be recovered exactly
- Generates spurious tuples
- Gives incorrect query results
- Avoided in good database design

---

# Common Exam Mistakes

❌ Thinking "more tables = better"

Not always. The decomposition must also be **lossless**.

---

❌ Thinking "joining always returns the original table"

Wrong.

Joining incorrectly decomposed tables may create **extra rows**.

---

❌ Confusing redundancy with lossless

A table may have redundancy, but decomposition is considered successful only if it is **lossless**.

---

# One-Line Revision

- **Decomposition** → Breaking a large table into smaller tables.
- **Lossless Decomposition** → Original table is recovered exactly after joining.
- **Lossy Decomposition** → Original table cannot be recovered exactly; fake or missing rows occur.
- **Lossless = Good Database Design**
- **Lossy = Bad Database Design**

---

# Quick Revision Box

✅ Decomposition = Divide large relation.

✅ Lossless = No information loss.

✅ Lossy = Information loss.

✅ Lossless generates **no spurious tuples**.

✅ Lossy may generate **spurious tuples**.

✅ Normalization aims for **lossless decomposition**.

---

# DBMS Notes
# Lossy vs Lossless Decomposition (Part 2)
## Functional Dependency • Keys • Lossless Conditions • Chase Test • Exam Tricks
### Topper Notes | Simplest Language | IBPS SO IT Officer | GATE | University

---

# Table of Contents

1. Quick Revision
2. Functional Dependency (FD)
3. Why FD is Important in Decomposition
4. Super Key
5. Candidate Key
6. Primary Key
7. Prime vs Non-Prime Attribute
8. Why Keys Decide Lossless or Lossy
9. Condition for Lossless Decomposition
10. Shortcut Rule
11. Mathematical Rule
12. How to Identify Lossless in 30 Seconds
13. Chase Test (Step by Step)
14. Solved Examples
15. Exam Tricks
16. Common Mistakes
17. Revision Sheet

---

# Quick Revision

Part 1 taught us:

- Decomposition means breaking a large table into smaller tables.
- Lossless means no information is lost.
- Lossy means information is lost or extra tuples (spurious tuples) appear.

Now the biggest question is:

> **How do we know whether a decomposition is lossless or lossy?**

For that, we need **Functional Dependency (FD)** and **Keys**.

---

# Functional Dependency (FD)

## Simple Definition

A Functional Dependency tells us:

> One attribute uniquely determines another attribute.

Notation:

```
A → B
```

Read as:

```
A determines B
```

or

```
Knowing A, we can always find B.
```

---

## Example 1

Student Table

| Roll | Name |
|------|------|
|101|Rahul|
|102|Amit|
|103|Priya|

Every Roll Number belongs to exactly one student.

So,

```
Roll → Name
```

Correct.

---

## Example 2

Employee Table

|EmpID|Department|
|-----|----------|
|1|IT|
|2|HR|

```
EmpID → Department
```

Correct.

---

## Wrong Functional Dependency

Can we say

```
Department → EmpID
```

No.

Why?

IT department has many employees.

One department cannot determine exactly one employee.

So this FD is incorrect.

---

# Easy Trick

Ask yourself:

> If I know the value on the left, can I always predict exactly one value on the right?

If YES

It is a Functional Dependency.

---

# Why Functional Dependency Matters

Lossless decomposition depends on Functional Dependencies.

Without FD,

you cannot determine whether decomposition is good or bad.

Think of FD as the **rules of the database**.

---

# Super Key

## Definition

A Super Key is any set of attributes that uniquely identifies every row.

It may contain extra attributes.

---

Example

Student

|Roll|Name|Phone|

```
Roll
```

uniquely identifies every student.

So,

```
Roll
```

is a Super Key.

But

```
Roll + Name
```

also uniquely identifies every student.

Still a Super Key.

```
Roll + Name + Phone
```

also works.

Still a Super Key.

---

# Memory Trick

Super Key

```
Unique
+

May contain extra attributes
```

---

# Candidate Key

Candidate Key means

> Minimum Super Key.

No unnecessary attributes.

---

Example

```
Roll
```

is enough.

So

Candidate Key = Roll

But

```
Roll + Name
```

contains an extra attribute.

So

NOT Candidate Key.

---

# Memory Trick

Candidate Key

```
Unique

AND

Minimum
```

---

# Primary Key

One Candidate Key selected by the database designer becomes

Primary Key.

---

Example

Candidate Keys

```
Email

EmployeeID
```

Suppose database chooses EmployeeID.

Then

Primary Key = EmployeeID

---

# Prime Attribute

Attribute that belongs to at least one Candidate Key.

---

Example

Candidate Key

```
Roll
```

Prime Attribute

```
Roll
```

---

# Non-Prime Attribute

Attribute not present in any Candidate Key.

Example

```
Roll

Name

Department
```

Candidate Key

Roll

Prime

Roll

Non-prime

Name

Department

---

# Why Keys Matter?

Suppose

Original Relation

```
R(A,B,C)
```

FD

```
A → B
```

Decompose

```
R1(A,B)

R2(A,C)
```

Notice

Common Attribute

```
A
```

A determines B.

A is a key in R1.

Therefore

Lossless.

---

# Biggest Rule of Lossless Decomposition

Suppose

```
R

↓

R1

R2
```

Common attributes are

```
R1 ∩ R2
```

If the common attribute can determine all attributes of at least one table,

then decomposition is

**Lossless**

---

# Mathematical Rule

For decomposition

```
R → R1,R2
```

Lossless if

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

This is the most important formula.

Memorize it.

---

# Simple Language Version

Look at the common column.

Ask

Can this common column identify one complete table?

If YES

Lossless.

If NO

Lossy.

---

# Shortcut Rule

Suppose

```
Student(Roll,Name,Department)
```

Split

```
StudentInfo(Roll,Name)

DepartmentInfo(Roll,Department)
```

Common Attribute

```
Roll
```

Roll identifies StudentInfo completely.

Hence

Lossless.

---

# Another Example

Original

```
R(A,B,C)
```

FD

```
A → B

A → C
```

Split

```
R1(A,B)

R2(A,C)
```

Common

```
A
```

A identifies R1

A identifies R2

Therefore

Lossless.

---

# Counter Example

Original

```
R(A,B,C)
```

Split

```
R1(A,B)

R2(B,C)
```

FD

```
A → B
```

Common Attribute

```
B
```

Can B identify R1?

No.

Can B identify R2?

No.

Therefore

Lossy.

---

# 30-Second Identification Trick

STEP 1

Find common attributes.

STEP 2

Check Functional Dependency.

STEP 3

Ask

Can common attribute determine all columns of one table?

YES

Lossless

NO

Lossy

---

# Visual Trick

```
      R1

A B

      ∩

A

      ∩

A C

      R2
```

Common Attribute

A

A determines R1

Lossless

---

# Chase Test

One of the favorite GATE questions.

Don't worry.

Let's learn from scratch.

---

# What is Chase Test?

A systematic method to verify whether decomposition is

Lossless

or

Lossy.

---

# When to Use Chase Test?

Use when

- Multiple Functional Dependencies
- Confusing decomposition
- Competitive exams
- GATE
- University theory papers

---

# Chase Test Steps

Suppose

```
R(A,B,C)
```

Decompose

```
R1(A,B)

R2(A,C)
```

FD

```
A → B

A → C
```

---

## Step 1

Create table

|Relation|A|B|C|
|---------|--|--|--|
|R1|a1|b1|c2|
|R2|a1|b2|c1|

Same attributes

same symbols

Missing attributes

different symbols

---

## Step 2

Apply Functional Dependencies.

FD

```
A → B
```

Since A is same

Make B same.

---

FD

```
A → C
```

Make C same.

---

Result

Everything becomes identical.

Hence

Lossless.

---

# Easy Way to Remember Chase Test

```
Same Left Side

↓

Make Right Side Same
```

Repeat until

No further change.

---

If one complete row becomes identical

Lossless.

Otherwise

Lossy.

---

# Solved Example 1

Relation

```
R(A,B,C)
```

FD

```
A → B

B → C
```

Split

```
R1(A,B)

R2(B,C)
```

Common

```
B
```

Can

```
B → R1 ?
```

No.

Need A also.

Can

```
B → R2 ?
```

Yes

Because

```
B → C
```

So B determines

(B,C)

Hence

Lossless.

---

# Solved Example 2

```
R(A,B,C)
```

FD

```
A → B
```

Split

```
R1(A,C)

R2(B,C)
```

Common

```
C
```

Can C determine R1?

No.

Can C determine R2?

No.

Lossy.

---

# Solved Example 3

Relation

```
Employee(EmpID,Name,Department)
```

FD

```
EmpID → Name

EmpID → Department
```

Split

Employee

```
(EmpID,Name)
```

Department

```
(EmpID,Department)
```

Common

EmpID

EmpID determines both tables.

Lossless.

---

# Solved Example 4

Original

```
(Student,Course)
```

Split

```
Student

Course
```

Common Attribute

None.

Immediately

Lossy.

---

# Super Shortcut

No Common Attribute

↓

Always Lossy

because natural join becomes Cartesian Product.

This is a favorite MCQ.

---

# Important Exam Tricks

## Trick 1

Common Attribute is Candidate Key

↓

Always Lossless

---

## Trick 2

No Common Attribute

↓

Lossy

---

## Trick 3

Intersection should determine one complete relation.

---

## Trick 4

Extra tuples after Join

↓

Lossy

---

## Trick 5

Exact original relation after Join

↓

Lossless

---

# Common Mistakes

❌ Thinking every decomposition is good.

Wrong.

Only Lossless decomposition is desirable.

---

❌ Looking only at number of tables.

Wrong.

Need Functional Dependency.

---

❌ Ignoring common attributes.

Intersection is the first thing to check.

---

❌ Confusing Candidate Key with Super Key.

Candidate Key

=

Minimum Super Key.

---

# Memory Hacks

## FD

```
Left Side

knows

Right Side
```

---

## Candidate Key

```
Minimum

Unique
```

---

## Super Key

```
Unique

May contain extras
```

---

## Lossless Formula

```
Common Attribute

↓

Must determine one complete table.
```

---

# Golden Formula (Most Important)

For

```
R → R1,R2
```

Lossless iff

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

Remember this formula for **IBPS SO**, **GATE**, **University exams**, and **interviews**.

---

# Quick Revision Sheet

✅ Functional Dependency means one attribute determines another.

✅ Super Key uniquely identifies tuples.

✅ Candidate Key is the minimum Super Key.

✅ Primary Key is a selected Candidate Key.

✅ Lossless decomposition requires the common attributes to determine at least one decomposed relation completely.

✅ If there is **no common attribute**, the decomposition is generally **Lossy**.

✅ Chase Test is a systematic method to verify lossless decomposition.

---

