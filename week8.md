# Week8

Aries makes database more reliable.

Atomicity, Consistency, Isolation, Durability.

Recovery manager guarantees Atomicity and Durability; Transaction model guarantees Consistency and Isolation.



## Buffer pool

Reduce traffic from slow device to fast device.

Eviction needs to use page, any modified pages should copied to the disk.

**Force** write: the moment write, don't keep it in the buffer catch, immediately write on disk. Therefore, it has poor response time and provides durability

**No Force**: make all modification in the memory. 

**Steal**: Need to create an empty space. Steal memory space for old page and give it to new page. Can have more throughout, but hard to atomicity.





## Log

Record REDO and UNDO information for every time update.

### **Write-Ahead Logging** protocol.

* Force the log record for new values for an update before data page gets to disk(steal); 


* Must write all log records to disk (force) for a Xact before commit.
* Guarantee Atomicity
* Guarantee Durability -> no update lost

ARIES algorithm is how log works



Each log records had a unique Log Sequence Number (LSN)

Each data page contains pageLSN

System keeps track of fulshedLSN -> how far is my log is written

Before a page is written, make sure pageLSN is <= flushedLSN



























---

END