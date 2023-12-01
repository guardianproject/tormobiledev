---
description: Tor + Pluggable Transports on iOS and macOS
---

# IPtProxyUI

You can find IPtProxy at: [https://github.com/tladesignz/IPtProxyUI-ios](https://github.com/tladesignz/IPtProxyUI-ios)

IPtProxyUI provides all things necessary to use the Pluggable Transports from the [IPtProxy](https://github.com/tladesignz/IPtProxy) library with Tor, preferrably via [Tor.framework](https://github.com/iCepa/Tor.framework).

It includes all necessary configuration, code to interact with Tor Project's MOAT/rdsys service to update the user's configuration and fetch lesser-known bridges and, of course, a ready-made UI to show to your users which can handle all of the above.

The UI is complete for your users to configure all aspects of the Transports. However, you're not obliged to use it. You can create your own and use the lower-level code only.

Additionally there's a helper class `IpSupport` which can aid in better supporting IPv6-only networks which are common with some mobile network carriers.
