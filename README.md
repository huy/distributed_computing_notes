## Distributed computing

**Fault tolerance**

One of the promise of distributed computing is fault tolerance by mean a computing system is resilient to a predicted and un predicted failure of its components. A degree of fault tolerance indicates which and how many components can fail under certain assumption without compromising the intended functionality of the system.

Formular is used for specifying of a fault tolerance system, e.g.

* `2*f + 1`: with `2*f + 1` components then the system can tolerate failure of `f` components
* `3*f + 1`: with `3*f + 1` components then the system can tolerate failure of `f` components

**Replicated machine**

If we view our system as a finite state machine - [FSM](http://en.wikipedia.org/wiki/Finite-state_machine), then one way to archive fault tolerance is maintain one or several replicated machine. Each replicated machine can be hosted in different physical box to be safe against hardware failure.

At the beginning all state machines are the same (in both state and transition functions) and events processed by one machine will be executed in exact order in other machine. 

To be consistent from client point of view, these replicas need to agree on a strict sequence of executed events at any point in time. This kind of agreement (also refered to as distrtibuted consesnsus) is addressed by employing distributed algorithm (aka protocol).

**Distributed consensus**

One of concern of distributed computing is how to reach an agreement among N parties. Parties comunicate with each other asynchronously using non reliable network in which message can be lost, duplicated, reordered. In extreme, a party may pass a false message to other either intentionaly or accidently, an phenomena described as byzantine problem.

Algorithm solving distributed consensus relies on quorums to make decisions. There are several distributed consensus algorithms and their implementation that are successfully deployed in practices.

Examples are

* Paxos - The very first algorithm that solves distributed consensus problem among replicated machines.
* RAF - Simplification of Paxos emphasize on understandability and easy to implement

**References**

* http://research.google.com/archive/chubby.html
* https://raftconsensus.github.io/

