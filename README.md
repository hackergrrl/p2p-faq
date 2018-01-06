# Peer-to-Peer Frequently Asked Questions

## Sounds great, but will it scale?

Yes. It is rare to find a p2p service that does not scale. They are distributed
systems by design, and most distributed systems are meant to scale. You could
say, then, that many distributed systems take cues from p2p systems in order to
scale properly. As a good example, Skype was built by the same engineers who
built Kazaa, and Skype internally used p2p distribution in order to alleviate
the load from any single node, and to save costs. Bittorrent also thrives in
situations where there are a high number of peers.

Like centralized systems, performance will suffer if the load is not
distributed. A torrent file with only one seed and thousands of leechers would
struggle to initially share to the first wave of peers. Unlike a centralized
system though, once that first wave of peers downloads a copy, the bandwidth for
that torrent data to be served grows exponentially.

## If websites are hosted on p2p, what happens when no peers are online?

...

## What about security? Somebody could share a hacked version of a p2p website?

...

## What about privacy? Everybody in the p2p network can see what I am looking at.

...

## p2p is great, but sometimes you need a single authoritative source of truth

...

## What if nazis take over the p2p network?

...

## What areas do modern p2p apps still struggle with?

Apps still seem to have a hard time managing resources, like CPU and network
bandwidth. If an app naively tries to download and replicate ALL of the data it
sees, it's easy for it to overwhelm the machine it's running on. Many apps still
have a ways to go in offering good controls for CPU and bandwidth use.

