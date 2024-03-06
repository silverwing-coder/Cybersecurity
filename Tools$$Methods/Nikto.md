<h6>ver. Sep-2022</h6>
<h2> Nikto</h2>

-   Open-source vulnerability scanner that performs comprehenisive tests against web servers for multiple items
-   Refer to

    [1. Nikto2 on CIRT.net](https://cirt.net/Nikto2)

    [2. GitHub: Nikto](https://github.com/sullo/nikto)

    [3. Kali: Nikto](https://www.kali.org/tools/nikto/)

---

```sh

# install Nikto if necessary (KaliLinux default)
sudo apt install nikto

nikto -Version
man nikto

nikto -host 10.6.6.23

# automate with nmap
nmap -p 80 10.1.1.0/24 -oG - | nikto -h -

```
