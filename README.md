# Stable_marriages
I'll try and implement a version of the **Nobel Prize-winning algorithm** for the stable marriage problem. It's called the [Gale-Shapley](https://en.wikipedia.org/wiki/Gale%E2%80%93Shapley_algorithm) algorithm AKA the "Deferred Acceptance" algorithm.

The Gale Shapley algorithm solves what's called the **Stable Marriage** Problem. Here is the problem framed as marrying men and women: 

> Given $n$ men and $n$ women, where each person has ranked all members of the opposite sex in order of preference, marry the men and women together such that there are no two people of opposite sex who would both rather have each other than their current partners. When there are no such pairs of people, the set of marriages is deemed stable.

This little model however is generally applied to more than marrying men and women. For example, it's the algorithm used to match newly graduated doctors with hospitals, and a variation on it matches kidney patients with organ donors in our hospital system.

The algorithmic question is, given lists of preferences as input, can we find a stable marriage? Can we even guarantee a stable marriage will exist for any set of preferences? The answer to both questions is yes, and it uses an algorithm called deferred acceptance.

Here is an informal description of the algorithm. It goes in rounds. In each round, each man “proposes” to the highest-preferred woman that has not yet rejected him. On the other side, each woman holds a reference to a man at all times. If a woman gets new proposals in a round, she immediately rejects every proposer except her most preferred, but does not accept that proposal. She “defers” the acceptance of the proposal until the very end.
