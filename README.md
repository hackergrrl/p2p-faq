# Peer-to-Peer Frequently Asked Questions

## Sounds great, but will it scale?

Yes. It is rare to find a p2p service that does not scale. They are distributed systems by design, and most distributed systems are meant to scale. You could say, then, that many distributed systems take cues from p2p systems in order to scale properly. As a good example, Skype was built by the same engineers who built Kazaa, and Skype internally used p2p distribution in order to alleviate the load from any single node, and to save costs.  

## If websites are hosted on p2p, what happens when no peers are online?

...

## What about security? Somebody could share a hacked version of a p2p website?

If cryptographic signatures come into play, this is not possible.

Consider a content-addressed system. In such systems, content is addressed via
a cryptographic hash which represents the content. For example, a file
containing "Hello World" gets a hash "648a6a6ffff".
If a peer now tries to fetch content from the network, it does so by asking
for the content of "648a6a6ffff".
If it gets sent this content, it can then verify with that same hash,
whether the content it got is the actual content it requested.

An attacker would be able to host malicious nodes in the network, but as the
node which _requests_ the content (your node) can verify that it got what it
expected.

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

