# Arti and Onionmasq on iOS

Currently, Arti on mobile is still quite experimental and not actively maintained.

The features it already has can be tried out on iOS with either using [Arti Mobile Experimental](https://gitlab.com/guardianproject/arti-mobile-ex) directly, or by using it embedded in [Tor.framework](https://github.com/iCepa/Tor.framework), which gives you the advantage of having some helper classes at hand.

There's a [Podspec](https://github.com/iCepa/Tor.framework/blob/pure\_pod/Arti.podspec), which supports that.

In your `Podfile:`

```ruby
pod 'Tor/Arti', :podspec => 'https://github.com/iCepa/Tor.framework/blob/pure_pod/Arti.podspec'
```

Said `Podspec` also contains an experimental version of [OnionMasq](https://gitlab.torproject.org/tpo/core/onionmasq), which contains Arti + IP packet routing (so you can use it on a `tun` device or Apple's [Network Extension API](https://developer.apple.com/documentation/networkextension) directly).&#x20;

At some point in the future this will probably replace the C-Tor + IPtProxy + leaf combination, which Orbot iOS currently uses.
