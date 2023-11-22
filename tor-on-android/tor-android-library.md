---
description: Integrating Tor directly into your mobile app
---

# Tor-Android library

Source repository: [https://github.com/guardianproject/tor-android/](https://github.com/guardianproject/tor-android/)

Easy to integrate as a Maven dependency

```
// dependencies {
    implementation 'info.guardianproject:tor-android:0.4.8.7'
    implementation 'info.guardianproject:jtorctl:0.4.5.7'
}
```

Bind to Tor as a Service

```
// bindService(new Intent(this, TorService.class), new ServiceConnection() {
            @Override
            public void onServiceConnected(ComponentName name, IBinder service) {

                TorService torService = ((TorService.LocalBinder) service).getService();

                Toast.makeText(MainActivity.this, "Got Tor control connection", Toast.LENGTH_LONG).show();
            }

            @Override
            public void onServiceDisconnected(ComponentName name) {

            }
        },BIND_AUTO_CREATE);
```
