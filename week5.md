# Week5

### Isolation

**Guarantees consistency** ->  Isolation guarantees consistency provided each transaction itself is consistent.

**Achieve isolation by sequentially** (sometime sequentially much faster than parallel -> no need for locks) 

<br />

<br />

<br />



---



<br />

These two rules can guarantee isolation.

<br />

## Dependency property

In a history sequence H, consisting of tuples of the form (T, action, object).  e.g. 	(T1,a1,O)

<br />

**Lost update**: a transaction write is ignored by another transaction. (WRITE -> WRITE conflict)

**Dirty read**: a transaction reads an object written by another transaction which again modifies the object afterwards. (WRITE -> READ Conflict)

**Non repeatable read**: a transaction reads an object twice and gets different values. (READ->WRITE conflict)

<br />

##### Share lock

For read, cannot write. Also called read lock. If one source is locked by share lock, other transaction only can add share lock to it. The share lock can generate the value is not be modified.

<br />

##### Exclusive lock

For read&write. 

If one source is locked by exclusive lock, other transaction cannot add any lock on it. 

<br />

**Well-formed transactions**: A transaction is well formed if all READ, WRITE and UNLOCK operations are covered earlier by appropriate LOCK operations. 

**Two phase transactions**: A transaction is two phased if all LOCK operations precede all its UNLOCK operations. (if you lock then unlock, you cannot lock again)

**wormhole**: a history is isolated if and only if it has no wormholes.

**Rollback theorem**: an update transaction that does an UNLOCK and then does a ROLLBACK is not two phases.

<br />

<br />

### Degree of isolation

The more locks you take, the poorer performance you have. 

#### Degree3:

* Perfect transaction model. Best isolation, true isolation. 
* Lock protocol is **two phase** and **well formed**.
* Two phase lock -> lock anything which you want to access, then do read and write.
* It is sensitive to the following conflicts:
  * write->write; write ->read; read->write

<br />

#### Degree2:

* no lost updates and no dirty reads. Response time lower than degree 3. Run much more parallel than degree 3
* Only apply phase 1 and phase 2 for XLCOKs.
* SLOCKs release immediately. XLOCKs no need to wait for a long time.
* Might Non repeatable reads
* It is sensitive to the following conflicts:
  * write->write; write ->read

<br />

#### Degree1:

* No SLOCK for reading. Reading no need for waiting.
* Two phase for excusive lock
* It is sensitive the following conflicts:
  * write->write;

<br />

#### Degree0:

* No two phase, no lock for reading
* Lock protocol is well-formed
* When writes, lock then and immediately release. High response.
* Ignores all conflicts.

<br />

<br />

<br />

<br />

<br />

<br />

---

END