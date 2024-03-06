<h6>ver. Sep-2022</h6>
<h2> Greenbone Vulnerability Manager (OpenVAS)</h2>

<h5><em> *** Recommend assigning sufficient resources: CPU(4-core) & RAM(8GB) ***</em></h5>

-   The OpenVAS has been renamed to Greenbone Vulnerability Manager (GVM)
-   Open-source vulnerability scanner that was created by Greenbone Networks
-   Includes services and tools that perform detailed vulnerability scanning against hosts and networks
-   Refer to

    [1. Kali-Linux: gvm (Greenbone Vulnerability Manager)](https://www.kali.org/tools/gvm)

    [2. Greenbone OpenVAS -> GVM](https://greenbone.github.io/docs/latest/background.html#history-of-the-openvas-project)

    [3. GitHub: OpenVAS](https://github.com/greenbone/openvas-scanner)

    [4. Geeksforgeeks Tutorial: OpenVAS](https://www.geeksforgeeks.org/installing-openvas-on-kali-linux/)

---

```sh

# install GVM of necessary (Kali Linux default)
sudo apt install gvm

sudo gvm-check-setup

# follow instructions until all error resolved
sudo runuser -u _gvm -- gvm-manage-certs -a -f
sudo systemctl start redis-server@openvas.service
sudo runuser -u _gvm -- greenbone-nvt-sync
sudo runuser -u _gvm -- greenbone-feed-sync --type SCAP
sudo runuser -u _gvm -- greenbone-feed-sync --type CERT

# if postgresql server is not on
sudo service postgresql start

sudo runuser -u postgres -- /usr/share/gvm/create-postgresql-database

## if error occurs, verify postgresql version and upgrade default version
# 1. install latest version of postgres
sudo pat upgrade -y
dpkg --get-selections | grep postgres
pg_lsculsters
# 2. Stop postgres before making any changes
sudo service postgresql stop
# 3. rename the new postgres version's default cluster
sudo pg_renamecluster 15 main main_pristine
# 4. upgrade the old cluster to the latest version
sudo pg_upgradecluester 14 main
# 5. make sure everything working again
sudo service postgresql start
pg_cluster
# 6. drop the old culster if necessary
sudo pg_dropculster 14 main --stop

# set gvm server user-id and pass-word
sudo runuser -u _gvm -- gvmd --create-user=user-id --password=pass-word

# if service invocation error sustained
sudo chmod 666 /var/log/gvm/openvas.log

# update and setup
sudo gvm-feed-update
sudo gvm-setup
sudo gvm-check-setup

# start gvm-server
sudo gvm-start
# 1. open a web browser
# 2. goto "localhost" and log-in with id and password of postgresql DB


# stop gvm-server
sudo gvm-stop


```

---
