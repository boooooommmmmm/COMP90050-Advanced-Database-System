# Week 1 & 2

Provide security and reliably storage.

ACID: most important part in database system



##### Performance depends on: 

* hardware
  * CPU
  * I/O
  * memory
  * network
* software
* database tuning
  * indexing
  * view
  * data duplication



SQL algorithm is efficient



Database technologies: Relational database systems (RDB) .

* reliable

Object Oriented (OO) Database Systems



Deductive database systems (DDBS)



Key-value pair based data base Systems



NoSQL (Not only SQL)

* Simple design, scale
* consistency



Cloud computing



----

<br />

<br />

# Exam part



Effective  memory access time:

**Hit ratio** = references in cache / total references
$$
EA = H*C + (1-H)*S
$$
H = hit ratio, C = cache access time; S = memory access time 

<br />
$$
Disk\  access\ time = seek\  time +  rotational\ time + transferlength/bandwidth
$$


<br />

Effective disk buffer cache access time:
$$
EA = H*C+(1-H)*S
$$
where H = hit ratio, C = buffer access time;  S = disk access time



## RAID

### RAID 0 (Block level Striping)

* Balanced i/o of disk drives
* MMTF/2

### RAID 1 (Mirroring)

* independency
* \*2 read, /2 write
* MMTF^2

### RAID 2 (bit level striping)

* contiguous bits of data of file
* striping takes place at bit level
* double transfer rate
* MMTF/2

### RAID 3 (Byte level striping)

* striping takes place at bytes level
* MMTF^2/3

### RAID 4 (Block level striping)

* striping takes place at block level
* MMTF^2/3
* any changes have to modify disk 3

### RAID 5 (Block level striping)

* Most common technology
* No dedicated disk for parity blocks, Parity blocks are also striped

### RAID 6

* Similar to RAID 5 except two parity bocks used



<br />

# ACID 

* Atomicity: A transaction’s changes to the state (Database) are atomic implying either all actions happen or none happen. All or nothing
* Consistency: A the transaction is a correct transformation of the state. Actions taken as a whole do not violate the integrity of the application state assuming transactions are correct programs.
* Isolation: Even when several transactions are executed simultaneously, it appears to each transaction T that others executed either happen before T or after  T but not at the same time.
* Durability: State changes committed by a transaction survive failures.

<br />

<br />

# Transaction processing

Transaction processing provides the following:

* Resource mangers 
* Durable state
* Transaction programming language



There are two types of message passing:

* session based - usually efficient and reliable for an interaction that requires several message transfers. Package comes sequence.
* datagrams - efficient for single message transfers. Only one package, just send it and do not care the receiver receive it or not.



<br />

<br />

---

END