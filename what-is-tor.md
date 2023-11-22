---
description: About Tor, Tor Project and Onion Routing
---

# What is Tor?

### About the Tor Project and History

The Tor Project, Inc, became a 501(c)(3) nonprofit in 2006, but the idea of "onion routing" began in the mid 1990s.

Just like Tor users, the developers, researchers, and founders who've made Tor possible are a diverse group of people. But all of the people who have been involved in Tor are united by a common belief: internet users should have private access to an uncensored web.

In the 1990s, the lack of security on the internet and its ability to be used for tracking and surveillance was becoming clear, and in 1995, David Goldschlag, Mike Reed, and Paul Syverson at the U.S. Naval Research Lab (NRL) asked themselves if there was a way to create internet connections that don't reveal who is talking to whom, even to someone monitoring the network. Their answer was to create and deploy the first research designs and prototypes of onion routing.

The goal of onion routing was to have a way to use the internet with as much privacy as possible, and the idea was to route traffic through multiple servers and encrypt it each step of the way. This is still a simple explanation for how Tor works today.

In the early 2000s, Roger Dingledine, a recent [Massachusetts Institute of Technology (MIT)](https://web.mit.edu/) graduate, began working on an NRL onion routing project with Paul Syverson. To distinguish this original work at NRL from other onion routing efforts that were starting to pop up elsewhere, Roger called the project Tor, which stood for The Onion Routing. Nick Mathewson, a classmate of Roger's at MIT, joined the project soon after.

From its inception in the 1990s, onion routing was conceived to rely on a decentralized network. The network needed to be operated by entities with diverse interests and trust assumptions, and the software needed to be free and open to maximize transparency and decentralization. That's why in October 2002 when the Tor network was initially deployed, its code was released under a free and open software license. By the end of 2003, the network had about a dozen volunteer nodes, mostly in the U.S., plus one in Germany.

Recognizing the benefit of Tor to digital rights, the [Electronic Frontier Foundation (EFF)](https://www.eff.org/) began funding Roger's and Nick's work on Tor in 2004. In 2006, the Tor Project, Inc., a 501(c)(3) nonprofit organization, was founded to maintain Tor's development.

In 2007, the organization began developing bridges to the Tor network to address censorship, such as the need to get around government firewalls, in order for its users to access the open web.

Tor began gaining popularity among activists and tech-savvy users interested in privacy, but it was still difficult for less-technically savvy people to use, so starting in 2005, development of tools beyond just the Tor proxy began. Development of Tor Browser began in [2008](https://lists.torproject.org/pipermail/tor-talk/2008-January/007837.html).

With Tor Browser having made Tor more accessible to everyday internet users and activists, Tor was an instrumental tool during the [Arab Spring](https://en.wikipedia.org/wiki/Arab\_Spring) beginning in late 2010. It not only protected people's identity online but also allowed them to access critical resources, social media, and websites which were blocked.

The need for tools safeguarding against mass surveillance became a mainstream concern thanks to the [Snowden revelations in 2013](https://www.theguardian.com/world/interactive/2013/nov/01/snowden-nsa-files-surveillance-revelations-decoded#section/1). Not only was Tor instrumental to Snowden's whistleblowing, but content of the documents also upheld assurances that, at that time, [Tor could not be cracked](https://www.wired.com/story/the-grand-tor/).

People's awareness of tracking, surveillance, and censorship may have increased, but so has the prevalence of these hindrances to internet freedom. Today, the network has [thousands of relays](https://metrics.torproject.org/) run by volunteers and millions of users worldwide. And it is this diversity that keeps Tor users safe.

We, at the Tor Project, fight every day for everyone to have private access to an uncensored internet, and Tor has become the world's strongest tool for privacy and freedom online.

But Tor is more than just software. It is a labor of love produced by an international community of people devoted to human rights. The Tor Project is [deeply committed](https://blog.torproject.org/tor-social-contract) to transparency and the safety of its users.

### About the Tor Protocol

Internet communication is based on a store-and-forward model that can be understood in analogy to postal mail: Data is transmitted in blocks called IP datagrams or packets. Every packet includes a source IP address (of the sender) and a destination IP address (of the receiver), just as ordinary letters contain postal addresses of sender and receiver. The way from sender to receiver involves multiple hops of routers, where each router inspects the destination IP address and forwards the packet closer to its destination. Thus, every router between sender and receiver learns that the sender is communicating with the receiver. In particular, your local ISP is in the position to build a complete profile of your Internet usage. In addition, every server in the Internet that can see any of the packets can profile your behavior.

The aim of Tor is to improve your privacy by sending your traffic through a series of proxies. Your communication is encrypted in multiple layers and routed via multiple hops through the Tor network to the final receiver. More details on this process can be found in this [visualization](https://support.torproject.org/https/https-1/). Note that all your local ISP can observe now is that you are communicating with Tor nodes. Similarly, servers in the Internet just see that they are being contacted by Tor nodes.

Generally speaking, Tor aims to solve three privacy problems:

**First**, Tor prevents websites and other services from learning your location, which they can use to build databases about your habits and interests. With Tor, your Internet connections don't give you away by default -- now you can have the ability to choose, for each connection, how much information to reveal.

**Second**, Tor prevents people watching your traffic locally (such as your ISP or someone with access to your home wifi or router) from learning what information you're fetching and where you're fetching it from. It also stops them from deciding what you're allowed to learn and publish -- if you can get to any part of the Tor network, you can reach any site on the Internet.

**Third**, Tor routes your connection through more than one Tor relay so no single relay can learn what you're up to. Because these relays are run by different individuals or organizations, distributing trust provides more security than the old [one hop proxy](https://support.torproject.org/about/how-is-tor-different-from-other-proxies/) approach.

Note, however, that there are situations where Tor fails to solve these privacy problems entirely: see the entry below on [remaining attacks](https://support.torproject.org/about/attacks-on-onion-routing/).
