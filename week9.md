# Week 9

### Checkpointing

Periodically, the DBMS creates a checkpoint, in order to minimize the time taken to recover in the event of a system crash.  Save some states, so that the recovery is fast.

dirty: the page in memory have more recently modified than in the disk. The current one is dirty.



Recovery: the analysis phase



Recovery: the Redo phase



no need log for recovery, do it in sequential. 



What happens if system crashes during analysis? -> redo analysis



### Distribute recovery

[see next note](week10.md)