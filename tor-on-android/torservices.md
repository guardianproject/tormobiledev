---
description: The new way to use Tor as a separate app
---

# TorServices

TorServices source code and app install links are available at: [https://guardianproject.info/apps/org.torproject.torservices/](https://guardianproject.info/apps/org.torproject.torservices/)

TorServices is a free proxy app that empowers other apps to use the internet more securely. It acts as a simple Tor “provider” for apps to hide their Internet traffic by encrypting it, then bouncing through a series of computers around the world. Tor is free software and an open network that helps you defend against a form of network surveillance that threatens personal freedom and privacy, confidential business activities and relationships, and state security known as traffic analysis.

You can check for TorServices being installed, and setup callbacks for status broadcasts using NetCipher, exactly as you would with Orbot. Sample code is [available on Gitlab](https://gitlab.com/guardianproject/torservices/-/blob/master/sample/src/main/java/org/torproject/torservices/sample/MainActivity.java?ref\_type=heads), with a snippet displayed below

```
OrbotHelper.get(this).addStatusCallback(new StatusCallback() {
            @Override
            public void onEnabled(Intent statusIntent) {
                setProxy();
                webView.loadUrl("https://check.torproject.org/");
            }

            @Override
            public void onStarting() {
                statusTextView.setText("starting....");

            }

            @Override
            public void onStopping() {
                statusTextView.setText("stopping....");

            }

            @Override
            public void onDisabled() {
                statusTextView.setText("disable....");

            }

            @Override
            public void onStatusTimeout() {
                statusTextView.setText("timeout....");

            }

            @Override
            public void onNotYetInstalled() {
                statusTextView.setText("not installed....");

            }
        });

```

