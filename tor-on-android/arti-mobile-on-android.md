---
description: Using Tor's new Rust-based runtime in your Android app
---

# Arti Mobile on Android

[Arti-Mobile-Ex](https://gitlab.com/guardianproject/arti-mobile-ex) is the current project for building and using the Arti (Tor in Rust) project within your mobile app. The repository is available at: [https://gitlab.com/guardianproject/arti-mobile-ex](https://gitlab.com/guardianproject/arti-mobile-ex)

#### To build for Android

* install Rust and Android Studio. Make sure you can run an Hello World with both.
* go in the common folder and run `make android`.
* take a coffee, or two.
* open the android folder in Android Studio or use gradle to build your app as usual.



### Sample Project for Android

There is a [sample Android Studio project](https://gitlab.com/guardianproject/arti-mobile-ex/-/tree/main/android/sample?ref\_type=heads) that demonstrates how easy it can be to use Arti within your Android app.

Once you have built and imported the Arti library into your project, all that you do to initialize it using default ports, all that you need to do is:

```
Arti.init(this);
```

From there, you can easily proxy any HTTP connection over Arti's built-in SOCKs proxy port

```
Proxy proxy = new Proxy(Proxy.Type.SOCKS, new InetSocketAddress(proxyHost, proxyPort));

HttpURLConnection connection = null;
URL url = new URL(targetURL);
connection = (HttpURLConnection)url.openConnection(proxy);
connection.setRequestMethod("GET");
```

You can also use the ProxyConfig class to enable WebView proxying, as well

```
ProxyConfig proxyConfig = new ProxyConfig.Builder()
           .addProxyRule("127.0.0.1:8118") //http proxy for tor
          .addDirect().build();

ProxyController.getInstance().setProxyOverride(proxyConfig, new Executor() {
            @Override
            public void execute(Runnable command) {
                //do nothing
            }
        }, new Runnable() {
            @Override
            public void run() {

            }
        });

```
