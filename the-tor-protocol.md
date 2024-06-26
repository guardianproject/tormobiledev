---
description: How Tor works at the packet and network level
---

# The Tor Protocol

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption><p><a href="https://unit42.paloaltonetworks.com/tor-traffic-enterprise-networks/">"Tor 101"</a> from Palo Alto Networks</p></figcaption></figure>

Internet communication is based on a store-and-forward model that can be understood in analogy to postal mail: Data is transmitted in blocks called IP datagrams or packets. Every packet includes a source IP address (of the sender) and a destination IP address (of the receiver), just as ordinary letters contain postal addresses of sender and receiver. The way from sender to receiver involves multiple hops of routers, where each router inspects the destination IP address and forwards the packet closer to its destination. Thus, every router between sender and receiver learns that the sender is communicating with the receiver. In particular, your local ISP is in the position to build a complete profile of your Internet usage. In addition, every server in the Internet that can see any of the packets can profile your behavior.

The aim of Tor is to improve your privacy by sending your traffic through a series of proxies. Your communication is encrypted in multiple layers and routed via multiple hops through the Tor network to the final receiver. More details on this process can be found in this [visualization](https://support.torproject.org/https/https-1/). Note that all your local ISP can observe now is that you are communicating with Tor nodes. Similarly, servers in the Internet just see that they are being contacted by Tor nodes.

Generally speaking, Tor aims to solve three privacy problems:

**First**, Tor prevents websites and other services from learning your location, which they can use to build databases about your habits and interests. With Tor, your Internet connections don't give you away by default -- now you can have the ability to choose, for each connection, how much information to reveal.

**Second**, Tor prevents people watching your traffic locally (such as your ISP or someone with access to your home wifi or router) from learning what information you're fetching and where you're fetching it from. It also stops them from deciding what you're allowed to learn and publish -- if you can get to any part of the Tor network, you can reach any site on the Internet.

**Third**, Tor routes your connection through more than one Tor relay so no single relay can learn what you're up to. Because these relays are run by different individuals or organizations, distributing trust provides more security than the old [one hop proxy](https://support.torproject.org/about/how-is-tor-different-from-other-proxies/) approach.

Note, however, that there are situations where Tor fails to solve these privacy problems entirely: see the entry below on [remaining attacks](https://support.torproject.org/about/attacks-on-onion-routing/).
