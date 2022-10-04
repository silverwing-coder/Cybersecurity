<h6>ver. Sep-2022</h6>
<h2> WiFi Adapter Setup on Kali Linux/VirtualBox</h2>

---

<h5>Adapter Model: TP-Link AC600</h5>
<h4>Setup Procedure</h4>

1. Install VirtualBox extension pack
2. Go to:
   Settings -> USB -> USB 2.0 Controller -> O.K.
3. Turn on Kali Linux and confirm the adapter is checked
   Devices -> USB -> Realtek 802.11ac WLAN Adapter
4. Install adapter driver

```sh
sudo apt update
sudo apt upgrade
lsusb
sudo apt install realtek-rtl88xxau-dkms
sudo reboot

```

5. Check if it works in the necessary modes

```sh
lsusb
iwconfig
# move to root privilege
sudo su
airmon-ng check kill
# monitor mode
iwconfig wlan0 mode monitor
# packet injection test
aireplay-ng --test wlan0
# AP mode check
airbase-ng -a 00:11:22:33:4:55 -essid "test_id" -c 11 wlan0

```
