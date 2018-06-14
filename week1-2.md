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



### Database technologies:

##### Simple le systems like UNIX le system

* Usually very fast
*  Can be less reliable
* Application dependent optimisation
* Hard to maintain (concurrency issues)
* Lack of features { many of the features exist in RDB need to be incorporated
  * unnecessary code development and potential increase in unreliability



##### Relational database systems (RDB) .

* Proven technology (over 40 years)
* Can be slow for some applications
* Very reliable
* Application independent optimisation
* Well suited applications related to commerce
* Now viable in many applications thanks to better implementations and optim-
  isations
* Some RDBs support OO model, e.g. Oracle, DB2
* Widely used



##### Object Oriented (OO) Database Systems

* Can be slow in some applications
* Reliable
* Limited application independent optimisation although some newer develop-

ments make them very suitable

* Well suited for applications requiring complex data
* XML based Database Systems are becoming dominant
* Many applications now use XML documents
* Some RDBs also support limited OO models and XML handling
* Seldom used nowadays



##### Deductive database systems (DDBS)

* Generalisation of RDBs, e.g. allow recursion
* No commercially available systems like OODBs
* Many applications do not require the expressive power of these systems 

  * e.g. commerce applications
* Many RDBs provide some of the functionality of deductive database systems
  * e.g. supporting transitive closure operation (SQL2)



##### Key-value pair based data base Systems

* Very fast, high parallel processing of large data
* MapReduce and Hadoop are examples
* Many applications do not require the expressive functionality of transaction

processing (e.g. web search, big data analysis)

* Atomic update at key-value pair level only



##### NoSQL (Not only SQL)

* Mechanism other than tabular relations
* A result of Web 2.0, Facebook, Amazon needs
* Simple design, high scalability
* Less consistency, more availability, partition tolerance and speed
* Allows replication
*  Eventual consistency



##### Cloud computing



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
* parity 

### RAID 4 (Block level striping)

* striping takes place at block level
* MMTF^2/3
* any changes have to modify disk 3
* Parity

### RAID 5 (Block level striping)

* Most common technology
* No dedicated disk for parity blocks, Parity blocks are also striped
*  bits are distributed among all disks 
* 5 disk and 3 disk

### RAID 6

* Similar to RAID 5 except two parity bocks used



<br />

# ACID 

* Atomicity: A transaction’s changes to the state (Database) are atomic implying either all actions happen or none happen. All or nothing
* Consistency: The transaction is a correct transformation of the state. Actions taken as a whole do not violate the integrity of the application state assuming transactions are correct programs.
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