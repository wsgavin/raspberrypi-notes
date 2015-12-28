# Raspberry Pi Notes

## Setup wifi

```
sudo iwlist wlan0 scan
sudo vi sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

Add the following lines to `sudo nano /etc/wpa_supplicant/wpa_supplicant.conf`

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