---
description: Summary of different ways an app can integrate with Tor
---

# All the Ways to Torify

### Build Tor into your app

It is now easier than ever to directly build Tor into your app, hiding all complexity of setup and configuration from your users. Whether your use [Tor-Android](../tor-on-android/tor-android-library.md), [Arti](../tor-c-tor-vs-arti-what.md), or [Tor.framework](../tor-on-ios/tor.framework-for-ios.md), there are many options ready to go. Apps like Tor Browser for Android do this today, to provide a seamless, integrated experience for browsing the web over Tor.

### Integrate with external Orbot or TorServices app

If you do not want to add the additional code complexity and size directly into your app, you can instead only active Tor features if the user has [Orbot](../tor-on-android/netcipher-with-orbot-legacy.md) or [TorServices](../tor-on-android/torservices.md) installed on their device. Apps like [F-Droid](../mobile-apps-with-tor.md), [Save by OpenArchive](../mobile-apps-with-tor.md), and [ReThinkDNS](../mobile-apps-with-tor.md) do this today, to enable proxying through Tor without having to build i n all of Tor.

### Implement Tor in a VPN or Network Extension

If you want to build your own VPN, or want to ensure all possible network traffic from your app (and even whole device) are automatically routed through Tor, then this might be the approach you take. Apps like Orbot do this today, to provide an easy Tor-based VPN for users.

### Run an OnionServices in your app

Using Tor, you can turn your app into a server, that any other Tor client can connect to. This enables you to host content and services just like you are on the open web, directly from your device. Apps like [OnionShare](../mobile-apps-with-tor.md), [Briar](../mobile-apps-with-tor.md) and [Quiet](../mobile-apps-with-tor.md) do this today to enable file sharing and chat.
