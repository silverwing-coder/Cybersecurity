<h6>ver. Sep-2022</h6>
<h2> Nmap and Zenmap</h2>

-   Active scanner for collectiong information about a victim by using tools such as port and vulnerability scanners
-   Refer to

    [1. Namp&Zenmap](https://nmap.org/)

    [2. Kali-Linux: Zenmap](https://www.kali.org/tools/zenmap-kbx/)

    [2. Hacker Target Tutorial](https://hackertarget.com/nmap-tutorial/)

---

```sh
# Zenmap install on Kali Linux
sudo apt install zenmap-kbx
zenmap-kbx

# Nmap host enumeration
nmap -T4 10.6.6.0/24

### CompTIA PenTest Reference ####

# Help menu
nmap -h
# TCP SYN scan
nmap -sS target-ip-address
# UDP scan
nmap -sU target-ip-address
# Operating system detection
nmap -O target-ip-address
# Service version detection
nmap -sV target-ip-address
# Verbose scan
nmap -v target-ip-address
# Very verbose scan
nmap -vv target-ip-address
# Save the scan result into a document format : reselts.txt
nmap -sV -O target-ip-address -oX results.txt
# Agressive scan: OS and version detection, script scanning and traceroute
nmap -A target-ip-address results.txt
# Timing level set: T0 ~ T5
nmap -T5 target-ip-address
# Scan specific port
nmap -p 80 target-ip-address
# Scan all ports
nmap -p- target-ip-address
nmap -p0-65535 target-ip-address
# Scan ports from 0 to 1000
nmap -p0-1000 target-ip-address

# NSE (Nmap Script Engine)
locate nmap
locate .nse | grep http
nmap --script /usr/share/nmap/scripts/ target-ip-address
# All nse script under vulnerabiliyt category
nmap --script vuln target-ip-address
# Scan without ping (skip host discovery)
nmap -Pn target-ip-address

### Example
nmap -sV -Pn -A -T4 target-address -oX noPing.txt


```
