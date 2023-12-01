---
description: >-
  Lyrebird/Obfs4proxy and Snowflake Pluggable Transports for iOS, MacOS and
  Android
---

# IPtProxy Pluggable Transports

You can find IPtProxy at: [https://github.com/tladesignz/IPtProxy/](https://github.com/tladesignz/IPtProxy/)

Both Lyrebird/Obfs4proxy and Snowflake Pluggable Transports are written in Go, which is a little annoying to use on iOS and Android. This project encapsulates all the machinations to make it work and provides an easy to install binary including a wrapper around both.

Problems solved in particular are:

* One cannot compile `main` packages with `gomobile`. Both PTs are patched to avoid this.
* Both PTs are gathered under one roof here, since you cannot have two `gomobile` frameworks as dependencies, since there are some common Go runtime functions exported, which would create a name clash.
* Environment variable changes during runtime will not be recognized by `goptlib` when done from within Swift/Objective-C. Therefore, sensible values are hardcoded in the Go wrapper.
* Snowflake and Lyrebird/Obfs4proxy are patched to accept all configuration parameters directly.
* Free ports to be used are automatically found by this library and returned to the consuming app. You can use the initial values for premature configuration, which is just fine in situations, where you can be pretty sure, they're going to be available (typically on iOS). When that's not the case (e.g. multiple instances of your app on a multi-user Android), you should first start the transports and then use the returned ports for configuration of other components (e.g. Tor).
