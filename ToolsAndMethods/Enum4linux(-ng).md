<h6>ver. Sep-2022</h6>
<h2> Enum4linux</h2>

-   Enumerating data from Windows and Samba Hosts
-   Refer to

    [1. GitHub: enum4linux](https://github.com/CiscoCXSecurity/enum4linux)

    [2. GitHub: enum4linux-ng](https://github.com/cddmp/enum4linux-ng)

    [3. Kali-Linux: enum4linux](https://www.kali.org/tools/enum4linux/)

---

```sh
# From Zenmap enumeration to Websploit: Gravemind -> SMB server
enum4linux -v 10.6.6.23

# enum4linux-ng installation
git clone https://github.com/cddmp/euem4linux-ng
cd enum4linux-ng
sudo apt install python3.10-venv
python3 -m venv venv
source venv/bin/activate
pip install wheel
pip install -r requirements.txt
# invoke enum4linux-ng
python3 enum4linux-ng.py -As 10.6.6.23


```
