## Distributed computing

**Fault tolerance**

One of the promise of distributed computing is fault tolerance by mean a computing system is resilient to a predicted and un predicted failure of its components. A degree of fault tolerance indicates which and how many components can fail under certain assumption without compromising the intended functionality of the system.

A example of specifying of a fault tolerance system are

* `2*f + 1`: if we have `2*f + 1` components then system can tolerate failure of `f` components
* `3*f + 1`: if we have `3*f + 1` components then system can tolerate failure of `f` components

**Distributed consensus**

One of concern of distributed computing is how to reach an agreement among N parties also refer to as distributed concensus. Parties comunicate with each other asynchronously using non reliable network in which message can be lost, duplicated, reordered.
In extreme, a party may pass a false message to other either intentionaly or accidently, an phenomena described as byzantine problem.

Algorithm solving distributed consensus relies on quorums to make decisions.


