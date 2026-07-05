# DBMS Notes
# Lossy vs Lossless Decomposition (Part 1)
## Topper Notes | Simplest Language | IBPS SO IT Officer | GATE | University | Placement

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

# What's Next (Part 2)

In Part 2, we will cover:

- Functional Dependency (revision)
- Candidate Key
- Super Key
- Why keys matter in decomposition
- Conditions for Lossless Decomposition
- Mathematical test for Lossless Decomposition
- Common shortcut rules
- Chase Test (step-by-step)
- Exam tricks to identify Lossless vs Lossy in under 30 seconds
- University, GATE, and IBPS SO style solved examples
