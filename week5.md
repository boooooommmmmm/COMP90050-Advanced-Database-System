# Week5

### Isolation

Guarantees consistency

achieve isolation by sequentially (sometime sequentially much faster than parallel -> no need for locks) 





**Lost update**: a transaction write is ignored by another transaction.

**Dirty read**

a transaction reads an object written by another transaction which again modifies the object afterwards.

**Non repeatable read**: a transaction reads an object twice and gets different values.



Share lock

Exclusive lock



Well-formed transactions: A transaction is well formed if all READ, WRITE and UNLOCK
operations are covered earlier by appropriate LOCK operations

Two phase transactions: A transaction is two phased if all LOCK operations precede
all its UNLOCK operations. 

