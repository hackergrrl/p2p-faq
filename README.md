# Peer-to-Peer Frequently Asked Questions

**N.B.** This FAQ focuses on the very nebulous term "p2p system". There's not a
single answer that maps exactly to *all* peer-to-peer systems; this FAQ does its
best to provide a general answer when possible, and provide concrete examples
where it makes sense.

## 1. Sounds great, but will it scale?

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

## 2. If websites are hosted on p2p, what happens when no peers are online?

*From @noffle:*

The same result as when a centralized website goes down: it isn't available.

The difference is that peer-to-peer networks distribute *the power to host*. I
could run a peer serving my website on a server. Instantly I have the same
website availability as a traditional centralized website. The difference is
that there may be many peers in the swarm that are also hosting my website, so
if my server goes down, the site will continue to be accessible through those
seeding peers.

*From @retrohacker:*

Many p2p systems, i.e. BitTorrent, are optimized for sharing popular content.
The more popular a piece of content, the more available the content becomes. The
less popular content is, the less available the content becomes. Popularity in
this case is the number of peers actively consuming and sharing a piece of
content. The ability to access any piece of content on a p2p network is limited
by the availability of peers, no peers no content.

If you share content on a p2p network that you have a vested interest in being
always-available, you must invest in maintaining your own highly available peers
that share this content. This is not dissimilar to a centralized network, in
that you must build highly available infrastructure to share your content.
However, unlike a centralized network, you're infrastructure is no longer a
single point of failure since you have the benefit of a p2p network supporting
you.

In the p2p model, you are not soley responsible for your uptime or performance.
If your system falls over, consumers of your content can still fetch from
another peer. If there is a spike in popularity of your content, peers will
share content amongst eachother reducing the burden on your infrastructure. In
many cases this can provide a better overall experience for consumers of your
content.

## 3. What about security? Somebody could share a hacked version of a p2p website?

*From @noffle:*

It depends what the security model of the system hosting the website uses. There
are two commonly tools I know of for ensuring that a copy of data you've
received from a potentially untrusted source is authentic:

1. You used the [hash](https://wikipedia.org/Hash_function) of the data to
   request from the p2p network. If so, the data you receive from a peer can be
   hashed, and that hash compared against the one used to make the request for
   the data. [IPFS](https://ipfs.io) and [Secure
   Scuttlebutt](https://scuttlebutt.nz) do this. A caveat is that the data is
   static: the hash never changes and thus neither can the data. A benefit is
   that content-addressable data can be safely cached indefinitely.

2. You used the [public key](https://wikipedia.org/Public_key_cryptography) of
   the author to request the data from the p2p network. The idea is that every
   version of the data is cryptographically signed by the data's author, so that
   any data you download will have a signature can be checked against the public
   key used to request the data. This guarantees that the data came from the
   author you expected, and also permits changes to that data, unlike with
   content-addressed above. [Dat](https://dat-project.org),
   [IPFS](https://ipfs.io) and [SSB](https://scuttlebutt.nz) all use this
   approach for dynamic data.

*From @matthiasbeyer:*

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

## 4. What about privacy? Everybody in the p2p network can see what I am looking at.

*TODO*

## 5. P2P is great, but sometimes you need a single authoritative source of truth

*From @matthiasbeyer:*

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

*From @noffle:*

If you are cryptographically signing the data you create (see #3), users can
request your content by your public key. In this way you are able to control
what data appears in this feed of data, but rely on potentially untrusted peers
to distributed that data.

By introducing a monotonic increasing sequence number to each new entry in the
signed feed, peers can be assured that no messages were suppressed or censored.

## 6. What areas do modern p2p apps still struggle with?

Apps still seem to have a hard time managing resources, like CPU and network
bandwidth. If an app naively tries to download and replicate ALL of the data it
sees, it's easy for it to overwhelm the machine it's running on. Many apps still
have a ways to go in offering good controls for CPU and bandwidth use.

