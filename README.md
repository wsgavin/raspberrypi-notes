# Raspberry Pi Notes

## Setup wifi

The following command will scan for available wifi networks.

```
sudo iwlist wlan0 scan
```

Example output:

```
pi@raspberrypi:~$ sudo iwlist wlan0 scan
wlan0     Scan completed :
          Cell 01 - Address: 90:72:40:1A:F7:7C
                    ESSID:"Your_SSID"
                    Protocol:IEEE 802.11bgn
                    Mode:Master
                    Frequency:2.437 GHz (Channel 6)
                    Encryption key:on
                    Bit Rates:144 Mb/s
                    Extra:rsn_ie=30140100000fac040100000fac040100000fac020000
                    IE: IEEE 802.11i/WPA2 Version 1
                        Group Cipher : CCMP
                        Pairwise Ciphers (1) : CCMP
                        Authentication Suites (1) : PSK
                    Quality=100/100  Signal level=58/100
```

Find the line with ESSID to see the available wifi network. Edit the `/etc/wpa_supplicant/wpa_supplicant.conf` file.

```
sudo vi sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

Add the following lines to the end of `/etc/wpa_supplicant/wpa_supplicant.conf`

```
network={
    ssid="Your_SSID"
    psk="Your_wifi_password"
}
```

Restart the interface.

```
sudo ifdown wlan0
sudo ifup wlan0
```