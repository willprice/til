# Raspberry Pi

## Headless Raspberry Pi via WiFi setup
(2017/09/17)

The raspberry pi be default disables SSH, to enable it on boot add an empty
file called `ssh` to the FAT `boot` partition, this will be detected by the pi
and will trigger the `sshd` to become enabled. See the [Raspberry Pi Foundation
Docs](https://www.raspberrypi.org/documentation/remote-access/ssh/) for more.


> If a wpa_supplicant.conf file is placed into the /boot/ directory, this will
> be moved to the /etc/wpa_supplicant/ directory the next time the system is
> booted, overwriting the network settings; this allows a Wifi configuration to
> be preloaded onto a card from a Windows or other machine that can only see the
> boot partition.

Later versions of Raspbian now copy a file `wpa_supplicant.conf` from `/boot`
to `/etc/wpa_supplicant/`. See [Raspberry Pi
blog](https://www.raspberrypi.org/blog/page/2/?fish#another-update-raspbian)
for details. Here's the file I used:

```
network={
    ssid="YOUR_SSID"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}
```
