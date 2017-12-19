# Peer-to-Peer Frequently Asked Questions

## Sounds great, but will it scale?

Yes. It is rare to find a p2p service that does not scale. They are distributed systems by design, and most distributed systems are meant to scale. You could say, then, that many distributed systems take cues from p2p systems in order to scale properly. As a good example, Skype was built by the same engineers who built Kazaa, and Skype internally used p2p distribution in order to alleviate the load from any single node, and to save costs.  

## If websites are hosted on p2p, what happens when no peers are online?

...

## What about security? Somebody could share a hacked version of a p2p website?

...

## What about privacy? Everybody in the p2p network can see what I am looking at.

...

## p2p is great, but sometimes you need a single authoritative source of truth

This is not true. Consider git: Each branch could be considered as source of
truth (or rather "point of truth").
Branches may depend on eachother, branches may be merged. Branches may _not_
depend on eachother (git can have multiple "orphan" branches) and may _not_ be
merged. Still, they are points of truth.
With p2p systems in a decentralized environment, this is true as well.
There might never be the _one_ version which is currently the point of truth,
but as long as versions of the system can be merged, this is not a problem.

Events in such a system can even be sorted chronologically via
[vector clocks](https://en.wikipedia.org/wiki/Vector_clock)
where each key is the unique peer hash.

There exists a technology which brings data types to the table which can exist
in a p2p system without ever needing a single source of truth. These types are
named [CRDT](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type)s.

## What if nazis take over the p2p network?

...

## What areas do modern p2p apps still struggle with?

Apps still seem to have a hard time managing resources, like CPU and network
bandwidth. If an app naively tries to download and replicate ALL of the data it
sees, it's easy for it to overwhelm the machine it's running on. Many apps still
have a ways to go in offering good controls for CPU and bandwidth use.

