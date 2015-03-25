## Distributed computing - Introduction of fault tolerance

**Fault tolerance**

One of the promise of distributed computing is fault tolerance by mean a computing system is resilient to a predicted and un predicted failure of its components. A degree of fault tolerance indicates which and how many components can fail under certain assumption without compromising the intended functionality of the system.

**State Machine Replication**

If we view our system as a finite state machine - [FSM](http://en.wikipedia.org/wiki/Finite-state_machine), then one way to archive fault tolerance is maintain one or several replicated machines. Each replicated machine can be hosted in different physical box to be safe against hardware failure.

At the beginning all state machines are the same (in both state and transition functions) and events processed by one machine will be executed in exact order in other machines. 

To be consistent from client point of view, these replicas need to agree on a strict sequence of executed events at any point in time. This kind of agreement (also refered to as distrtibuted consesnsus) is addressed by employing distributed algorithm (aka protocol).

**Distributed consensus**

One of concern of distributed computing is how to reach an agreement among N parties. Parties comunicate with each other asynchronously using non reliable network in which messages can be lost, duplicated, reordere; parties can crash, restart. In extreme, a party may pass a false message to other either intentionaly or accidentally, an phenomena described as byzantine problem. 

Algorithm solving distributed consensus relies on quorums to make decisions. There are several distributed consensus algorithms and their implementation that are successfully deployed in practices.

Examples of distributed consensus protocols are

* Paxos - The very first algorithm that solves distributed consensus problem among replicated machines.
* RAF - Simplification of Paxos emphasize on understandability and easy to implement.

It is prove that under asumption of no party lying (they can however fail arbitrarily),`2*f + 1` replicas can tolerate failure of `f` replicas. The system of `3*f + 1` replicas can safely work if no more than `f` crash or fabricate messages passed to other in any malicious way.

**Ad hoc protocol**

There are a lot of Ad hoc protocols trying to solve distributed consensus problem. They are usually embedded inside cluster management software. Most of them assume the control of reliable network and lack of proof about correctness in the face of network partition.

**References**

* http://research.google.com/archive/chubby.html
* https://raftconsensus.github.io/
* http://en.wikipedia.org/wiki/Byzantine_fault_tolerance

