# Week 4

<br />

###  ACID

**Atomicity**: all or nothing. When apply for transaction, all of them are done or not at all. 

**Consistency**: the most difficult; If transaction is parallel, Preserving an Invariant

**Isolation**: every transactions have to wait until last transaction finish modifying. ->locking protocol -> sequential 

**Durability**: either entire block is written correctly on disk or the contexts of the block is unchanged. -> use version number and write sequentially.

<br />

### CRC: Cyclic Redundancy Check

<br />

## Transaction models

### Flat

Can be a very long running transaction. Any failure of transaction requires lot of unnecessary.



### Nested

Commit rule: 

* A subtransaction can either commit or abort,however, commit cannot take place unless the parent itself commits.
* Subtransactions have  A, C, and I properties but not have Dproperty unless all its ancestors commit.
* Commit of a sub transaction makes its results available only to its parents.

Roll back Rules

* If a subtransaction rolls back all its children are forced to roll back.

Visibility Rules

* Changes made by a sub transaction are visible to the parent only when the sub transaction commits. Whereas all objects of parent are visible to its children. Implication of this is that the parent should not modify objects while children are accessing  them. This is not a problem as parent is not run in parallel with its children.

<br />

<br />

<br />

<br />

<br />