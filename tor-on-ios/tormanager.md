---
description: The easiest way to integrate Tor and Pluggable Transports into your app.
---

# TorManager

You can find TorManager at: [https://github.com/tladesignz/TorManager](https://github.com/tladesignz/TorManager)

This library bundles all building blocks to integrate Tor into your app:

* Tor.framework using
  * C-Tor
  * GeoIP files
* IPtProxyUI using
  * Lyrebird Pluggable Transport
  * Snowflake Pluggable Transport
  * Auto-configuration support via Moat/RdSys services
  * Auto-configuration support for IPv4/IPv6 cappable networks
* OrbotKit to detect and interact with a running Orbot

Plus

* A "smart connect" algorithm to automatically step through the transports to find a connection in hostile environments.
* Provide correct \`WKWebView\` and \`URLSession\` proxy configurations.

\
