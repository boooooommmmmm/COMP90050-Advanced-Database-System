# Week 6

Something about presentation...

----

LectureSet5

---

Phantoms and Predicate locks:

When doing query, system will generate shared lock to satisfied tuples. When generate locks, there might have new transaction to insert some values.

Use predicate locks and page locks can solve this problem



### Predicate locks  谓词锁

Read and write sets can be defined by predicates (e.g. Where clauses in SQL statements) and associate a lock with such a set.



**problems**



### Granularity Locks  粒度锁

#### Intention Lock  意向锁