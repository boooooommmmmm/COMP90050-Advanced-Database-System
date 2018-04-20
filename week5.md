# Week5

### Isolation

Guarantees consistency

achieve isolation by sequentially (sometime sequentially much faster than parallel -> no need for locks) 

<br />

<br />

<br />

##### Share lock

For read, cannot write. Also called read lock. If one source is locked by share lock, other transaction and only add share lock to it. The share lock can generate the value is not be modified.

<br />

##### Exclusive lock

For read&write

---



<br />

**Well-formed transactions**: A transaction is well formed if all READ, WRITE and UNLOCK
operations are covered earlier by appropriate LOCK operations

**Two phase transactions**: A transaction is two phased if all LOCK operations precede
all its UNLOCK operations. (if you lock then unlock, you cannot lock again)

<br />

These two rules can guarantee isolation.

<br />

---

### Dependency property

In a history sequence H, consisting of tuples of the form (T, action, object).  e.g. 	(T1,a1,O)

<br />

**Lost update**: a transaction write is ignored by another transaction. (WRITE
-> WRITE conflict)

**Dirty read**: a transaction reads an object written by another transaction which again modifies the object afterwards. (WRITE -> READ Conflict)

**Non repeatable read**: a transaction reads an object twice and gets different values. (READ->WRITE conflict)

<br />

wormhole

<br />

##### Degree of isolation

the more locks you take, the performance is poorer

Degree3:

Perfect transaction model. Best isolation, true isolation. Two phase lock -> lock anything which you want to access, then do read and write.

<br />

Degree2:

no lost updates and no dirty reads. Response time lower than degree 3.

<br />

Degree1:



<br />

Degree0:

No two phase, lock then immediately release. High response.

Ignores all conflicts.

<br />

<br />

<br />

<br />

<br />

<br />