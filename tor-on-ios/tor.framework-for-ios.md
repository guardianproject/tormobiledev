---
description: Using Tor the way Apple intends you to
---

# Tor.Framework for iOS

You can find Tor.Framework at: [https://github.com/iCepa/Tor.framework](https://github.com/iCepa/Tor.framework)

### Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

### Installation

Install build tools via [Homebrew](https://brew.sh/):

```
brew install automake autoconf libtool gettext
```

Tor is available through [CocoaPods](https://cocoapods.org/). To install it, simply add the following line to your Podfile:

If you use dynamic frameworks, use the root spec:

```
use_frameworks!
pod 'Tor', '~> 408'
```

(or `Tor/GeoIP` - see below.)

If you need to add it as a static library, you will need to add it from a modified podspec:

```
pod 'Tor', :podspec => 'https://raw.githubusercontent.com/iCepa/Tor.framework/pure_pod/TorStatic.podspec'
```

Currently static library support is unstable. You might encounter build issues. Every contribution to fix this is welcome!

(or `Tor/GeoIP` - see below.)

### Usage

Starting an instance of Tor involves using three classes: `TORThread`, `TORConfiguration` and `TORController`.

Here is an example of integrating Tor with `NSURLSession`:

```
TORConfiguration *configuration = [TORConfiguration new];
configuration.ignoreMissingTorrc = YES;
configuration.cookieAuthentication = YES;
configuration.dataDirectory = [NSURL fileURLWithPath:NSTemporaryDirectory()];
configuration.controlSocket = [configuration.dataDirectory URLByAppendingPathComponent:@"control_port"];

TORThread *thread = [[TORThread alloc] initWithConfiguration:configuration];
[thread start];

NSData *cookie = configuration.cookie;
TORController *controller = [[TORController alloc] initWithSocketURL:configuration.controlSocket];

NSError *error;
[controller connect:&error];

if (error) {
    NSLog(@"Error: %@", error);
    return;
}

[controller authenticateWithData:cookie completion:^(BOOL success, NSError *error) {
    if (!success)
        return;

    [controller addObserverForCircuitEstablished:^(BOOL established) {
        if (!established)
            return;

        [controller getSessionConfiguration:^(NSURLSessionConfiguration *configuration) {
            NSURLSession *session = [NSURLSession sessionWithConfiguration:configuration];
            ...
        }];
    }];
}];
```

#### GeoIP

In your `Podfile` use the subspec `GeoIP` or `StaticGeoIP` instead of the root spec:

```
use_frameworks!
pod 'Tor/GeoIP'
```

or

```
pod 'Tor/GeoIP', :podspec => 'https://raw.githubusercontent.com/iCepa/Tor.framework/pure_pod/TorStatic.podspec'
```

The subspec will create a "GeoIP" bundle and install a run script phase which will download the appropriate GeoIP files.

To use it with Tor, add this to your configuration:

```
TORConfiguration *configuration = [TORConfiguration new];
configuration.geoipFile = NSBundle.geoIpBundle.geoipFile;
configuration.geoip6File = NSBundle.geoIpBundle.geoip6File;
```

