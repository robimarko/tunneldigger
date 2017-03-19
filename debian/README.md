# tunneldigger-client

This folder contains all the files for creating package for [wlan Slovenija tunneldigger](https://github.com/wlanslovenija/tunneldigger) client.

---
### Building package

Tested under Debian Jessie.

* Install the following packages: `debhelper fakeroot gcc libc6-dev libnl-genl-3-dev make`
* Change the directory to repository root.
* Create package: `fakeroot debian/rules binary`

---
### Configuration

All the configuration of the VPN client stays in `/etc/tunneldigger.conf`. UUID, IFACE and SERVER are mandatory parameters.
To setup IP address for IFACE, edit `/etc/network/interfaces` as

```
allow-hotplug digger0
iface digger0 inet static
  address 10.254.x.y/32
```

Then the client could be started by `/etc/init.d/tunneldigger start`.

