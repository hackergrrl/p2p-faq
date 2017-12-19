# Peer-to-Peer Frequently Asked Questions

## Sounds great, but will it scale?

Yes. It is rare to find a p2p service that does not scale. They are distributed systems by design, and most distributed systems are meant to scale. You could say, then, that many distributed systems take cues from p2p systems in order to scale properly. As a good example, Skype was built by the same engineers who built Kazaa, and Skype internally used p2p distribution in order to alleviate the load from any single node, and to save costs.  

## If websites are hosted on p2p, what happens when no peers are online?

Many p2p systems, i.e. BitTorrent, are optimized for sharing popular content. The more popular a piece of content, the more available the content becomes. The less popular content is, the less available the content becomes. Popularity in this case is the number of peers actively consuming and sharing a piece of content. The ability to access any piece of content on a p2p network is limited by the availability of peers, no peers no content.

If you share content on a p2p network that you have a vested interest in being always-available, you must invested in maintaining your own highly available peers that share this content. This is not dissimilar to a centralized network, in that you must build highly available infrastructure to share your content. However, unlike a centralized network, you're infrastructure is no longer a single point of failure since you have the benefit of a p2p network supporting you.

In the p2p model, you are not soley responsible for your uptime or performance. If your system falls over, there is still a chance for consumers of your content to fetch from another peer. If there is a spike in popularity of your content, peers will share content amongst eachother reducing the burden on your infrastructure. In many cases this can provide a better overall experience for consumers of your content.

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

