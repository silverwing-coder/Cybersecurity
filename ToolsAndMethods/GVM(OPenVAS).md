<h6>ver. Sep-2022</h6>
<h2> Greenbone Vulnerability Manager (OpenVAS)</h2>

-   Open-source vulnerability scanner that was created by Greenbone Networks
-   Includes services and tools that perform detailed vulnerability scanning against hosts and networks
-   Refer to

    [1. Kali-Linux: gvm (Greenbone Vulnerability Manager)](https://www.kali.org/tools/gvm)

    [2. Greenbone OpenVAS -> GVM](https://greenbone.github.io/docs/latest/background.html#history-of-the-openvas-project)

    [3. GitHub: OpenVAS](https://github.com/greenbone/openvas-scanner)

    [4. Geeksforgeeks Tutorial: OpenVAS](https://www.geeksforgeeks.org/installing-openvas-on-kali-linux/)

---

```sh

# install GVM of necessary (KaliLinux default)
sudo apt install gvm

gvm-check-setup -h
# follow instructions until all error resolved
sudo runuser -u _gvm -- gvm-manage-certs -a -f
sudo systemctl start redis-server@openvas.service
sudo runuser -u _gvm -- greenbone-nvt-sync
sudo runuser -u _gvm -- greenbone-feed-sync --type SCAP
sudo runuser -u _gvm -- greenbone-feed-sync --type CERT
sudo runuser -u postgres -- /usr/share/gvm/create-postgresql-database
# set gvm server user-id and pass-word
sudo runuser -u _gvm -- gvmd --create-user=user-id --password=pass-word
# if service invocation error sustained
sudo chmod 666 /var/log/gvm/openvas.log
sudo gvm-check-setup -h

# update and setup
sudo gvm-feed-update -h
sudo gvm-setup -h

# start gvm-server
sudo gvm-start --help
# stop gvm-server
sudo gvm-stop -h


```
