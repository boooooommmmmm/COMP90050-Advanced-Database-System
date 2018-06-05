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

Hit ratio = references in cache / total references
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

### RAID 5 ()



---

END