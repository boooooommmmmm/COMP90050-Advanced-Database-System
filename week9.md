# Week 9

> The Recovery Manager guarantees Atomicity & Durability. 

<br />

### Checkpointing

Periodically, the DBMS creates a checkpoint, in order to minimize the time taken to recover in the event of a system crash.  Save some states, so that the recovery is fast.

dirty: the page in memory have more recently modified than in the disk. The current one is dirty.



Recovery: the analysis phase



Recovery: the Redo phase



no need log for recovery, do it in sequential. 



What happens if system crashes during analysis? -> redo analysis



Atomicity & Durability

 

#### Abort

* Before undo, must have a lock on data.
* Before resotring old value of a page, write a Compensation Log Record (CLR).
  * extra field: undonextLSN -> points to the next LSB to undo.
  * CLR never undone
* Write "end" log at the end of UNDO



### Recovery

1. Find checkpoint in the master record.
2. Three phase
   1. Analysis -> scan all logs -> copy two tables from checkpoint || if see one of the log record is "end", remove this Xact from Xact table. || add new Xact to Xact table. || if page is not in the dirty page table, write it in the dirty page table.
   2. REDO -> redo everything from smallest recLSN in dirty page table to crash point
   3. UNDO ->
3. 

### Distribute recovery

[see next note](week10.md)