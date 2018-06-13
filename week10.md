# Week 10

ARIES can be done locally, and globally apply two phase locking.

### Distribute recovery

Master node (coordinator node): the node which transaction starts.

Two phase protocol 

Ensure that all sub-transactions of distributed transaction must commit or none must commit. (All or none)



New kinds of failure ->

 

##### Two phase commit protocol

Phase 1:

- The coordinator sends a **prepare message** to each subordinate
- On receiving a prepare message a subordinate decides to either commit or abort its sub-transaction. It force-writes an abort or prepare log record and sends yes or no  message to the coordinator.

<br />

Phase 2:

- If the coordinator  receives all “yes” messages from all subordinates it force-writes a commit log record and then sends commit messages to all subordinates. If it receives even one no message or does not receive a message within some specified time it force-writes an abort log and sends abort message to all subordinates.
- When a subordinate receives an abort message it force-writes an abort log record and sends an acknowledgement to the coordinator. It aborts the sub-transaction.

<br />

If we have a commit or abort log of T, the status is clear. We redo or undo T as in centralized database systems. The coordinator needs sending messages to its subordinates  abort or commit messages until it receives acknowledgements from them.

If we have only prepare log for T but no commit or abort log record and the site is a subordinate we must repeatedly contact the the coordinator  to respond for commit or abort instruction. After receiving a message the rest of actions are 2PC.

If there no prepare, commit, abort log records, the subordinate aborts the transaction unilaterally. If the site is the coordinator it then has to inform all subordinates to abort their subtransaction.

<br />

A

---

END