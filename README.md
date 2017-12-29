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

...

## What if p2p technology is used by "bad actors"?

A very common concern with P2P technologies is that they aid crime, piracy, pedophilia, and other bad activities. The upside of not having an authority is also its unfortunate downside. That said, this aspect of information systems is overestimated when compared to other technologies like cars, weapons, hard drives, and kitchen cutlery. Terrorist attacks are carried out often through cars and common knives, yet it seems absurd to common sense that there would be global realtime surveillance of all cars and kitchen knives in order to prevent crimes. On the other hand, information systems by themselves cannot directly cause any physical harm. The absurdity of censoring cars and cutlery should extend also to information systems, or at least the discourse around security and crime prevention should get the priorities right and first address the root causes, the supporting incentives, the real weapons, and the tradeoffs involved.

More about this: https://theintercept.com/2015/11/17/u-s-mass-surveillance-has-no-record-of-thwarting-large-terror-attacks-regardless-of-snowden-leaks/

## What areas do modern p2p apps still struggle with?

Apps still seem to have a hard time managing resources, like CPU and network
bandwidth. If an app naively tries to download and replicate ALL of the data it
sees, it's easy for it to overwhelm the machine it's running on. Many apps still
have a ways to go in offering good controls for CPU and bandwidth use.

