# Week8

Aries makes database more reliable.

Atomicity, Consistency, Isolation, Durability.

Recovery manager guarantees Atomicity and Durability; Transaction model guarantees Consistency and Isolation.



## Buffer pool

Reduce traffic from slow device to fast device.

Eviction needs to use page, any modified pages should copied to the disk.

**Force** write: the moment write, don't keep it in the buffer cache, immediately write on disk. Therefore, it has poor response time and provides durability

**No Force**: make all modification in the memory. 

Therefore, good response time, durability is a problem -> system crash 

=> write as little as possible, in a convenient place, at commit time

**Steal**: Need to create an empty space. Steal memory space for old page and give it to new page. 

Can have more throughout, but hard to atomicity.

<br /><br />

## Log

Record REDO and UNDO information for every time update.

An ordered list of REDO/UNDO actions

### **Write-Ahead Logging** protocol (WAL)

* **Force the log record** for new values for an update before data page gets to disk(stolen); 


* Must write all log records to disk (force) for a Xact before commit.
* Guarantee **Atomicity**
* Guarantee **Durability** -> no update lost

ARIES algorithm is how log works



Each log records had a unique **Log Sequence Number** (LSN)

Each data page contains **pageLSN**

System keeps track of **flushedLSN** -> how far is my log is written

Before a page is written, make sure pageLSN is <= flushedLSN



#### Transaction table

One entry per active Xact

Contains XID, status, lastLSN

#### Dirty Page Table

Tells which pages need to be flushed, which do not 

One entry per dirty page in buffer pool

Contains recLSN



### Checkpointing

minimize the time of recovery.

---

END