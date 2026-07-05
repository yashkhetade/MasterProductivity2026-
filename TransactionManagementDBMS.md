# TransactionManagementDBMS



#### transaction refers to a sequence of one or more operations (such as read, write, update, or delete) performed on the database as a single logical unit of work.

Transaction: When a user performs a money transfer, several operations occur, such as:

#### 1)Reading the account balance of the sender.

#### 2)Writing the deducted amount from the sender’s account.

#### 3)Writing the added amount to the recipient’s account.


# The primary aim of transaction management in a Database Management System (DBMS) is to ensure data integrity, reliability, and consistency. It achieves this by guaranteeing that all database operations are executed as a single, logical unit of work, particularly in multi-user environments or during system failures.Transaction management systems achieve these goals by strictly enforcing the ACID properties:

#  ACID Properties of Transaction
#### Transactions in DBMS must ensure data is accurate and reliable. They follow four key ACID properties:

#### 1) Atomicity: A transaction is all or nothing. If any part fails, the entire transaction is rolled back. Example: While transferring money, both debit and credit must succeed. If one fails, nothing should change.

#### 2) Consistency: A transaction must keep the database in a valid state, moving it from one consistent state to another. Example: If balance is ₹1000 and ₹200 is withdrawn, the new balance should be ₹800.

#### 3) Isolation: Transactions run independently. One transaction’s operations should not affect another’s intermediate steps. Example: Two users withdrawing from the same account must not interfere with each other’s balance updates.

#### 4) Durability: Once a transaction is committed, its changes stay even if the system crashes. Example: After a successful transfer, the updated balance remains safe despite a power failure.

# Transaction States 
LINK - https://www.geeksforgeeks.org/dbms/transaction-states-in-dbms/


# Schedule 
LINK - https://www.geeksforgeeks.org/dbms/types-of-schedules-in-dbms/

## There are 2 types of Schedules 
a) Serial b) Parallel

## a) Serial  Schedule

It is used to acheive data consistency

Here Transactions will  be completed one by one following a sequence

lets say we have 4 transactions t1,t2,t3,t4 

first t1 will execute completely then t2 ....t4 

Eg- ATM Machine ( At a time only one person can withdraw money from one ATM )

Disadvantage -
Waiting time is too much

So we use  b)Parallel Schedule -

## b)Parallel Schedule

Here Transactions will  be completing parallely

Eg - sbi website (while using sbi website we dont check how many people are using sbi website we simply use it )


