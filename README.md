# How to set static IP for wlan


## 1. Check available network
```
$ sudo iwlist wlan0 scan

```

## 2. Set wpa_supplicant.conf
```
$ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

country=GB # Country of UK

network={
    ssid="your-networks-SSID"
    psk="your-networks-password"
    scan_ssid=1 # option for hidden network
}
```

## 3. Set dhcpcd.conf
```
$ sudo nano /etc/dhcpcd.conf

#Add below codes at the end of file

# wire LAN
interface eth0
static ip_address=xxx.xxx.xxx.xxx
static routers=xxx.xxx.xxx.xxx
static domain_name_servers=xxx.xxx.xxx.xxx

# WiFi
interface wlan0
static ip_address=xxx.xxx.xxx.xxx
static routers=xxx.xxx.xxx.xxx
static domain_name_servers=xxx.xxx.xxx.xxx
```


## 4. Check network connection status
```
$ iwconfig
$ ifconfig


```

## Reference
[1] https://electrondust.com/2017/11/25/setting-raspberry-pi-wifi-static-ip-raspbian-stretch-lite/

[2] https://webnautes.tistory.com/903



# Pi monitoring

https://github.com/XavierBerger/RPi-Monitor


# The internet sharing from WiFi to ethernet port

https://raspberrypi.stackexchange.com/questions/48307/sharing-the-pis-wifi-connection-through-the-ethernet-port
