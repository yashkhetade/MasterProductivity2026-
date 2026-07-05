# TransactionManagementDBMS

#### transaction refers to a sequence of one or more operations (such as read, write, update, or delete) performed on the database as a single logical unit of work.

Transaction: When a user performs a money transfer, several operations occur, such as:

#### 1)Reading the account balance of the sender.

#### 2)Writing the deducted amount from the sender’s account.

#### 3)Writing the added amount to the recipient’s account.



#  ACID Properties of Transaction
#### Transactions in DBMS must ensure data is accurate and reliable. They follow four key ACID properties:

#### Atomicity: A transaction is all or nothing. If any part fails, the entire transaction is rolled back. Example: While transferring money, both debit and credit must succeed. If one fails, nothing should change.

#### Consistency: A transaction must keep the database in a valid state, moving it from one consistent state to another. Example: If balance is ₹1000 and ₹200 is withdrawn, the new balance should be ₹800.

#### Isolation: Transactions run independently. One transaction’s operations should not affect another’s intermediate steps. Example: Two users withdrawing from the same account must not interfere with each other’s balance updates.

#### Durability: Once a transaction is committed, its changes stay even if the system crashes. Example: After a successful transfer, the updated balance remains safe despite a power failure.
