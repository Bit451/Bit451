# Bit451

Bit451 is an open source decentralized/distributed anonymous p2p media network. It has been characterized as "YouTube meets BitTorrent meets Bitcoin".

![logo][logo]

[logo]: https://raw.githubusercontent.com/Bit451/Bit451/master/img/bit451-logo-100.png "Bit451 logo"

## Synopsis

Bit451 is comprised of multiple open source projects working together as one: a video browsing interface, a streaming BitTorrent protocol, and a specialized distributed database are its primary components. You, as a Bit451 user, will have the option to simply access the network directly from your browser, no additional setup required - or, to run a light, streamlined service to help host and contribute to the Bit451 network. Website creators can also easily tap into and serve Bit451 to their visitors using the same light setup configured to their liking.

As for the Bit451 network itself, it will have all the features you have come to know and love: user accounts/profiles, favorites, ratings, subscriptions, playlists, search, recommendations, and much more. The network is community-based, so the users and content you interact with is determined by your preferences and the users you trust. If you don't specifically know or "trust" any users starting out, don't worry, you're not alone and the default settings will work just great. Bit451 will also introduce an automatable cryptocurrency payment plugin system, so that content consumers and producers can buy, sell, and host content for their favorite coins.

At this point you may be wondering, that all sounds great but [what's so wrong with YouTube?](#youtube). (Yes, Bit451 can even read your mind! Pretty amazing so far, right?..)

_Feedback on any and all aspects of Bit451 are strongly desired and encouraged!_ Please join in to [Discuss](#discuss), [Donate](#donate), and [Contribute](#contribute)!

## Inspiration

The name Bit451 was inspired by _Fahrenheit 451_, a dystopian novel by Ray Bradbury published in 1953 which presents a future society where books are outlawed and "firemen" burn any that are found. A small community, intent on preserving the books, memorizes them to be recreated for future generations. The proper pronunciation of the number is "four five one" according to Bradbury.

### YouTube

The primary catalyst behind this idea is the increasing prevalence of issues and concerns with YouTube:

* censorship (via YouTube themselves, government removal requests, invalid copyright claims, "trusted flaggers", etc)
* trackability (view history trails, etc)
* requirement of email, phone, validation, etc
* Google+ forced integration
* annoying ads popping up throughout videos
* unknown future impositions
* features are always dictated by one company
* YouTube is a centralized entity

To be sure, YouTube has on the whole provided an important service to the internet community, and has the right to do as it wishes within its domain. But hasn't the time has come to unleash the freedom and creativity of _all of us_ into the content sphere?!

Many of these complaints could also extend to other current media powerhouses (Vimeo, Soundcloud, etc), but YouTube garners the most enthusiasm and is the prime focus.

### BitTorrent

BitTorrent is a technology before its time, the full potential of which has likely not yet been fully realized. Streaming BitTorrent content is the next step in its evolution, and along with it, the Bit451 network.

### Bitcoin

Bitcoin has sparked the internet's imagination. It has enabled not only new forms of commerce, but of communication, transmission, etc, in ways never dreamed of before, and Bit451 will take that to the next level.

## Similar Technologies and Projects

### WeTube

[WeTube](https://github.com/wetube/wetube-web) is a "Decentralized p2p, free, uncensored media provider". While this project is a step in the right direction, it also raises multiple concerns:
* _It is a "Distributed Autonomous Corporation" (DAC)_: This adds a level of complexity to the model which will likely confuse or scare away many potential users, as well as distract from the main focus.
* _It is dependent on its own currency, "MediaCoins"_: Creating a new currency seems to be outside the scope of a proper media network; it is more efficient and effective to focus on the media network aspect, let currency developers compete, and find ways to integrate payments as needed while remaining currency neutral.
* _It reinvents the wheel with "Bitcloud"_: Development of a brand new storage protocol named Bitcloud is the backbone of the project and must be completed before WeTube can be created. While there are benefits to creating a new protocol, they don't seem to outweigh the benefits of building on a tried-and-true protocol like BitTorrent.
* _It is too rigid_: More centralized and closed dev team and processes, its own hosted wiki and forum sites, etc, seem to have made its evolution (so far) a bit sluggish. On the other hand, Bit451 aims to have a more flexible and ad-hoc approach: development is open to all, auditable by all, and rewarded via bounties (see [Contribute](#contribute)); discussions are encouraged to occur in proven mediums (Reddit/Facebook/Twitter/etc) rather than its own separate website area so as to abate the doldrum effect.

WeTube may find its strengths in some of these areas, and hopefully it will; however, the overall vision for the project simply differs significantly from Bit451.

## Development and Technical Details

### Methodology

The main Components can each be separate projects to be forked and merged. Bounties will be divvied out proportionally based on completion of each project; for example, if Murray completes 50%, then Lew forks Murray's project and completes the other 50%, Murray and Lew will each receive 50% of the bounty. Unit tests are strongly encouraged.

When submitting a code change (_including to readme or other documentation!_), send a [pull request](https://help.github.com/articles/using-pull-requests), then post it in the primary Bit451 discussion area for community review; technical discussion of the pull request is encouraged to take place in the [pull request discussion](https://help.github.com/articles/using-pull-requests#pull-request-discussion) area. After it passes and is accepted, a waiting period of approximately one week will occur before bounties are paid out so that other developers can review the code. If it is found that code has been copied from another developer without credit, bounties will not be paid to the plagiarizer, but rather to the original developer.

Draw.io is the recommended online service for UML. Suitable UML diagram XMLs and their PNGs should be added to /uml.

Bit451.org will be used for the [GitHub Pages](https://help.github.com/articles/user-organization-and-project-pages) (github.io) Project Page to serve this readme from the base Bit451 project, via the [automatic generator](https://help.github.com/articles/creating-pages-with-the-automatic-generator), using Jekyll. Bit451.com will be used for the Project Page to serve the live Bit451 Portal, since it is static/browser-based. Bit451.net use is TBD. These are initial planned uses.

### Components

#### Phase 1 Development

The goal of this phase is to create a standardized, usable, aesthetic, browser-based frontend which can access the content network.

##### Portal

The browser/viewport/gateway. This is the interface used to access and interact with content from the network. This should be usable on a local machine (via a local engine) as well as hosted from a server, where it can be additionally configured/customized.

__MediaDrop__

MediaDrop is a modular video, audio, and podcast publication platform which can be extended with plugins: "The Web's Open Source Video Platform".

__Action Item__: Fork MediaDrop to _Bit451 Portal_. Slim it down to just the "client-side" interface.

_See Also_
* MediaDrop
  * http://mediadrop.net/
  * http://demo.mediadrop.net/
  * https://github.com/mediadrop/mediadrop

##### File Transfer

This is the protocol by which content files will be transmitted. The BitTorrent protocol network should be sufficient. Tying into this existing network has many advantages including established roots, wide user base, infinite content waiting to be brought to the masses, development community, etc.

Even though BitTorrent will be used, development should keep in mind the possibility of switching to or adding additional protocols in the future (i.e. remain as protocol-agnostic as possible).

_See Also_
* https://en.wikipedia.org/wiki/BitTorrent_%28protocol%29
* https://en.wikipedia.org/wiki/Anonymous_P2P
* https://en.wikipedia.org/wiki/Freenet
* https://en.wikipedia.org/wiki/I2P
* https://en.wikipedia.org/wiki/Tor_%28anonymity_network%29

##### Portal Gateway

This is the content bridge between the File Transfer network and the Portal.

__WebTorrent__
WebTorrent is a streaming torrent client for the browser using WebRTC. The Project Goal is to build a browser BitTorrent client that requires no install (no plugin/extension/etc.) and fully-interoperates with the regular BitTorrent network.

Since WebTorrent is web-first, it's simple for users who do not understand .torrent files, magnet links, NATs, etc. By making BitTorrent easier, it will be accessible to new swathes of users who were previously intimidated, confused, or unwilling to install a program on their machine to participate.

__Action Item__: Fork WebTorrent to _Bit451 Portal Gateway_. Implement any necessary additional functionality.

_Alternative:_

__Btapp.js__
The BitTorrent project Btapp.js can be used to bring the BitTorrent network to the browser. This project integrates with the BitTorrent Torque browser plugin or a number of other common software clients. For the purposes of this project let us assume that the Torque browser plugin is used, as it is the simplest way for the user to click-and-go.

A demo site/project called [oneHash](https://github.com/bittorrenttorque/onehash.com) exists to show some Btapp.js capabilities. It works directly hosted from the Github project, however, the domain is expired. You can still [try it here](http://bittorrenttorque.github.io/onehash.com/), or you can edit your computer's hosts file and point onehash.com to Github's IP (currently 192.30.252.153) as noted in [Setting up a custom domain with GitHub Pages](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages#apex-domains).

oneHash demonstrates the ability to stream torrent content via the browser. Currently only audio streaming is functional; video streaming is not yet completed as noted in the [Code Snippets](http://labs.bittorrent.com/developers/torque/code-snippets.html#file-streaming) page. If this is still the case by the time Bit451 development begins, it will need to be implemented.

_See Also_
* WebTorrent
  * https://github.com/feross/webtorrent
* Btapp.js
  * http://btappjs.com/
  * https://github.com/bittorrenttorque/btapp
  * https://github.com/bittorrenttorque/onehash.com
  * http://labs.bittorrent.com/developers/torque/api-visualizer.html
* https://en.wikipedia.org/wiki/WebRTC
* http://webp2p.org/
* https://shareit.5apps.com/
* https://en.wikipedia.org/wiki/Libtorrent#Piece_picker

#### Phase 1 Results

Via the static web files hosted locally or on any website (including the Github project page), users can now tap into and stream any media file on the BitTorrent network using the Bit451 Portal interface.

#### Phase 2 Development

The goal of this phase is to implement attributes of the Bit451 overlay network. The database uses trusted timestamping to verify data changes (most recently timestamped data trumps). A thin client will be implemented to connect the Bit451 network to the BitTorrent network and to allow Bit451 to be run server-side so site owners can provide their visitors with client-less access to the Bit451 network by retrieving/transcoding/caching/serving content.

##### Bit451 Service

This is the user connection to the Bit451 network. It can also enable servers in retrieving/transcoding/caching/serving content and serving it directly to their visitors in the browser, replacing the need for potential users to use a BitTorrent client and download data to their computer.

Bit451 servers can configure which content they wish to serve: from any users in their network, from Subscriptions only, from Favorites only, etc.

Video transcoding/serving is already built into the Bit451 Portal system, so it simply needs to be adapted for Bit451's architecture.

A similar GUI client such as Bitcoin or qBittorrent can be looked to as a starting point, and stripped down to what's needed.

As much as possible this should be decoupled from the Bit451 components' specific architectures.

_See Also_
* https://github.com/bitcoin/bitcoin
* https://github.com/qbittorrent/qBittorrent
* https://github.com/spesmilo/electrum

##### Distributed Data

The core of the Bit451 overlay network is its distributed data system. Options to store and access this data: 1) distributed databases (DDB), 2) distributed hash tables (DHTs). Option 1, DDB, is the Bit451 method of choice. It will be used in a conceptually new and exciting manner for P2P networks. The replication method devised is modeled on the concept of communities and community-based trust.

__OrientDB__
OrientDB is web ready (natively supports HTTP/RESTful protocol/JSON), cross-platform, embeddable (with local mode to bypass the server), has a footprint of only about 1MB for the full server, is well-supported/documented, supports drivers for Javascript (among others), database- and record-level security, and distributed architecture.

A primary functionality to be implemented for Bit451 is a security layer to: sign and verify records, selectively determine which records to query from/replicate, identify/block malicious nodes, etc.

Bit451 will embed the database in a thin wrapper client and interact via its Javascript driver. Each node acts as a server and represents an Account. Each record should be signed with a hash of ALL its fields (including ID, timestamp, and Account ID, etc) and public and private key, and then when verifying simply remove the signature (sig) and check against it. The client should enforce incoming data integrity, rate limit/protect against DoS attacks, etc (basically act as database gatekeeper).

Database connections should also be authenticated so that, for example, a hosted Bit451 installation cannot rely on a single naive user as its direct database connection/server. The user should also have the option to allow unauthenticated connections, i.e. to be an open host.

The last known IP/port for each node will, at least in this Phase, be stored in the Account record. Each time a node reconnects it will update its IP/port in its Account record (if it has changed), sign it, and replicate it to the network. It will also update its own TCP/IP member list after replicating *from* the network. This way the network always knows the most current connection to each node.

Accounts can also verify themselves to their web domain to engender trust (like a certification, or "cert"). For example, if the user of Account 123 is affiliated with foo.com, a DNS TXT record of "123" could be set at bit451.foo.com; then, the Account's cert field set to bit451.foo.com. Now when viewing Account 123, an Ajax DNS lookup is done at bit451.foo.com, and when successful, foo.com is shown as the certified domain.

The database structures used are typically regarded as database "tables" which have "fields"; in OrientDB these are actually called classes, and have properties. Records are accessible network-wide but security is record-level.

Each created Bit451 account will have self-owned classes, both vertices and edges. These will be replicated (read-only) across nodes on a determined basis: for each account a node networks with, said account's classes are replicated on that node.

Accounts can also Recommend other Accounts. Whereas Subscribe denotes a personal preference ("I want to watch this Account"), Recommend denotes an interpersonal reference ("I think others should watch this Account"). Likewise, Accounts can Mimic another Account's Recommendations, meaning that it will include all of that Account's Recommendations in its network (minus any Accounts it has ignored). Therefore, Subscribe will replicate one Account, and Mimic will replicate many Accounts.

The nodes *which replicate an account* are its Replication Network (R-Net). The nodes *which an account replicates* are its Transmission Network (T-Net), since it transmits them. Each R-Net and T-Net will include at least one node (itself). Note that *-Nets usually aren't necessarily bi-directional; for example, if Account 1 subscribes to Account 2, and Account 2 subscribes to Account 3, then node 1's T-Net is {1,2} and R-Net is {1}, node 2's T-Net is {2,3} and R-Net is {1,2}, and node 3's T-Net is {3} and R-Net is {2,3}.

A replication Hook will be used to replicate only records from one's T-Net (aggregation of one's Subscriptions, Recommendations, and Mimics, minus Ignores).

_Bootstrapping_

Because of the community-oriented nature of Bit451 networks, "bootstrapping" is not, in the conventional sense, necessary. Rather, new users will simply Subscribe (network with) and/or Mimic (network with connections of) the Account(s) they trust. Ideally a new user can simply Mimic a trusted Account from their community, and will instantly join the network of all of that Account's Recommendations.

_Account Recovery_

In the event that a private key is compromised, there should be a recovery method. Traditional methods such as email aren't suitable, and a new ID can't simply be generated since the account is tied to the ID. 

The solution is a master public key (MPK)/[hardened child public key](https://bitcoin.org/en/developer-guide#hardened-keys) scheme. The MPK will be the Account ID. Then, a child public key is used to sign records. The lowest key should be used first.

To recover the account, the user simply "burns" their current key. Records are then signed with the next-highest key. When the replication filter verifies records, it must first simply verify that the signing key is valid for the Account ID, and then, the highest key should win. This means the user has the ability to burn as many keys as needed; their account is never unrecoverable, since the use of hardened keys means that a compromised child private key does not compromise the master private key.

In order to resolve the event that a user's whole account is simply lost rather than compromised (ex: computer crash), accounts should be generated from a [deterministic wallet](https://en.bitcoin.it/wiki/Deterministic_wallet) seed, or master private key, similar to the [Electrum seed](https://electrum.org/seed.html). When creating a new account, the user is highly encouraged to record their seed somewhere safe. Bit451 Accounts, then, are somewhat comparable to Bitcoin wallets, at least insofar as functionality within the client. Also see [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki).

_Data Integrity_

Incoming replication data will hit a Hook which will verify each record's sig and, if forged, add the IP to its blacklist.

Deletions are a special case: records should have their "deleted" bit set by the owner; the deleted bit should always be queried against. Records should not be actually deleted from the database, since deleted records cannot be verified by the replication filter after deletion.

__Action Item__: Fork OrientDB to _Bit451 Database_. Implement any default config changes (group name/password, database name/password, etc) and other necessary modifications.

_Notes_
* Hot change of distributed configuration not available until 2.0 (https://github.com/orientechnologies/orientdb/wiki/Distributed-Sharding#limitation)

_See Also_
* OrientDB
  * https://en.wikipedia.org/wiki/OrientDB
  * https://github.com/orientechnologies/orientdb
  * https://github.com/orientechnologies/orientdb/wiki/Distributed-Sharding
  * https://github.com/orientechnologies/orientdb/wiki/Distributed-Architecture
  * https://github.com/orientechnologies/orientdb/wiki/Distributed-Architecture-Lifecycle
  * https://github.com/orientechnologies/orientdb/wiki/Security#record-level-security
  * https://github.com/orientechnologies/orientdb/wiki/Hook
  * https://github.com/orientechnologies/orientdb/wiki/Javascript-Driver
* https://en.wikipedia.org/wiki/Distributed_database
* https://en.wikipedia.org/wiki/Distributed_data_store
* https://en.wikipedia.org/wiki/Document-oriented_database
* [Bitcoin: Digital signatures](https://www.youtube.com/watch?v=Aq3a-_O2NcI)
* Other Popular DDBs
  * https://github.com/voldemort/voldemort
  * https://github.com/apache/cassandra
  * https://github.com/mongodb/mongo

_The following features will be elements of the Distributed Data system._

###### Accounts

Each Account represents a user, similar to profiles or channels. Properties include ID, name, about, favorites[], ratings[], subscriptions[], recommendations[], ignores[], mimics[], address (IP/port), cert (DNS TXT record), created, updated, deleted?, key, sig.

* Favorites: Each Favorite represents a reference to a Content.
* Ratings: Each Rating represents a reference to a Content (similar to a Like/Dislike or Upvote/Downvote, i.e. binary).
* Subscriptions: Each Subscription represents a reference to an Account, which the user wishes to subscribe to.
* Recommendations: Each Recommendation represents a reference to an Account, which the user wishes to recommend to others.
* Ignores: Each Ignore represents a reference to an Account, which the user wishes to ignore.
* Mimics: Each Mimic represents a reference to an Account, which the user wishes to mimic (copy/imitate) the Subscriptions, Recommendations, and/or Ignores of.

###### Content

Each Content represents a user-created reference to a torrent. Properties include ID, Account ID, torrent ID, name, description, tags[], type{video, audio, image, text, other}, created, updated, deleted?, key, sig.

Any user can, of course, add any existing torrent they wish. Bit451 will also introduce a brief template (with flags) to add to your new torrent which essentially verifies you as the owner.

###### Search

Since Bit451 data is stored in a DDB, this is relatively simple, as searches are just a query algorithm (DHT searches would be more complex).

_See Also_
* https://en.wikipedia.org/wiki/BitTorrent_%28protocol%29#Decentralized_keyword_search
* https://en.wikipedia.org/wiki/YaCy

#### Phase 2 Results

At this point users can log into and participate in Bit451 via a small app on their local machine, or they can guest browse Bit451 content via hosted Bit451 sites.

#### Phase 3 Development

The goal of this phase is to complete/enhance/granularize the Bit451 functionality and user experience. More technical details of this phase will be fleshed out as development progresses.

##### Anonymity

Provide ability to disable last known IP/port field in Account records, essentially allowing nodes to push/replicate data without being able to be connected to.

Strive to work with Tor, Freenet, I2P, etc.

##### Payments

A plugin API should be implemented to enable plugins (short scripts) to be written for cryptocurrencies and other payment systems, which can tie into various Bit451 hooks, allowing automated hosting agreements and payments.

Each Content record (and, of course, its torrent data) is hosted only on those nodes which choose to do so. This can include:
* The content's creator
* A user who likes the content and wants to help host it
* A user who will help host the content in exchange for a fee
* A user who will pay for permission to host the content (i.e. distributor; think Netflix)

Etc. In this way, content is hosted to the extent which it is demanded.

##### Distributed Data Additions

###### Reputation

Community interactions, such as Payments, require a level of trust. Reputation will enable users to judge the reliability of other users within their community. A good/bad/neutral rating could be associated with each Payment made via Bit451.

###### Hashtags

Tagging and searching of Content and Accounts via Hashtags.

###### Playlists

Can be stored locally initially, and eventually via optionally (paid?) remotely hosted protocol.

###### Similar Accounts/Content

Graph depth can be explored to find similar data to recommend to the user.

##### Bit451 Lite

Provides the ability to _fully_ participate in Bit451 actions (creating/modifying accounts/content, etc) directly via the browser using Javascript, so the user is not required to run the Bit451 Service to access the network.

#### Phase 3 Results

Bit451 complete. It is now a fully-featured, browser-based, distributed media network.

#### Post-Development

At this point we proceed with any new additions, bug fixes, etc. Some additional ideas include:

* Hooking into other networks such as Freenet (and other file sharing darknets) in addition to BitTorrent

### More Technical Links

* https://en.wikipedia.org/wiki/Distributed_hash_table
* https://en.wikipedia.org/wiki/Mainline_DHT
* https://en.wikipedia.org/wiki/Kademlia
* https://en.wikipedia.org/wiki/Anonymous_P2P
* https://en.wikipedia.org/wiki/Darknet_%28file_sharing%29
* https://en.wikipedia.org/wiki/Freenet
* https://en.wikipedia.org/wiki/Tor_%28anonymity_network%29
* https://en.wikipedia.org/wiki/Magnet_URI_scheme
* https://en.wikipedia.org/wiki/Cryptocurrency
* https://en.bitcoin.it/wiki/Blockchain
* https://en.bitcoin.it/wiki/Wallet
* https://unhosted.org/
* http://edtechdev.wordpress.com/2013/05/10/serverless-unhosted-nobackend/ [see: WebP2P section]

## UML

![Fig. 1](https://raw.githubusercontent.com/Bit451/Bit451/master/uml/bit451-network-community.png)
Fig. 1: Example of a network "community"

## Contribute

There is essentially little-to-no "official" development team, as development is crowdsourced, ad hoc, and decentralized. In fact, the community as a whole is the dev team. This means that _anyone_ is able to contribute and collaborate in whatever ways work best for them. With the existence of Github, code can be forked and built upon any number of times by any number of contributors until a working solution is created. Solutions will then be audited, tested, and assessed by the community before being accepted.

The primary reason to contribute to Bit451 is simply because you believe in the idea and want to make it happen; but an additional reason is that, to the extent possible, Bit451 will be _bounty-driven_. A significant amount of Bitcoin donations raised (as much as possible after paying other costs) will be used for Bitcoin bounties on Bit451's projects, both directly and via [Bountysource](http://www.bountysource.com/).

If a deeply established, respected, and community-loved open source dev(s) were to volunteer for the role of official Bit451 code gatekeeper, and the Bit451 community overwhelmingly supported it, that would be cool.

_Now let us go and ignite a firestorm, planting the technological seedlings of the future over a trail of obsolete overgrowth!_

## Roadmap / Timeline

3 Phases; the goal is ~1 month per phase (after initial discussion/planning phase). It should be completed by the end of the year. Yes, this is ambitious, but very much possible!

## Goals and Features

* be as ambitious as possible and push the envelope... but still work!
* improve and reuse other open source projects as possible
* don't reinvent the wheel
* cryptocurrency neutrality
* best practices and conventions, clean code, organization
* abstraction, inheritance, code reuse
* standardized, usable, aesthetic
* browser-based, unhosted/serverless, decoupled from specific frameworks/languages/etc as much as possible
* elegance and simplicity
* visionary
* far-reaching implications, not only on immediate systems like media but on greater internet-wide concepts and processes

## Discuss

* http://www.reddit.com/r/Bit451/
* https://www.facebook.com/Bit451
* https://twitter.com/Bit451
* #Bit451
* http://bitcointalk.bit451.org

## Donate

* https://coinbase.com/Bit451
* https://www.indiegogo.com/individuals/8110381/campaigns

## Architect

Calen Fretts is a schemer, dreamer, believer, fighter, doer, troublemaker, idealist, voluntaryist, and many other -ists and -ers. Basically he's probably just crazy.

## License

MIT.

## /Bit451

http://Bit451.org
https://github.com/Bit451

Bit451 should be used morally.

"Here's to the crazy ones. The misfits. The rebels. The troublemakers. The round pegs in the square holes. The ones who see things differently. They're not fond of rules. And they have no respect for the status quo. You can quote them, disagree with them, glorify or vilify them. But the only thing you can't do is ignore them. Because they change things. They push the human race forward. And while some may see them as the crazy ones, we see genius. Because the people who are crazy enough to think they can change the world, are the ones who do."
