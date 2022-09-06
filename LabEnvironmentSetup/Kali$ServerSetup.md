<h6>Ver. Aug-2021.</h6>

### Kali Linux Server Setup

**_School of Arts and Science, Carolina University_**

---

#### 1. Install Kali Linux on a Virtual Machine

-   <h5>Option-1: Download and Install VMware and Kali Linux separately </h5>

    -   Download [_VMware Workstation Player(Free Edition preferred)_](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html)
    -   Install VMware for non-commercial use
    -   Download [_Kali Bare Metal Installer Edition_](https://www.kali.org/get-kali/#kali-bare-metal)(kali-linux-2021xxxxxx.iso)
        -   Refer to [installation document](https://www.kali.org/docs/installation/hard-disk-install/)
        -   Thre is no problem to setup with default optionss
        -   Your PC/Laptop spec. will affect the performance of virtual machine
    -   Procedure

    1.  Open VMware Workstation Player
    2.  Create a New Virtual Machine -> Installer disc Image file(iso) -> Select Downloaded Kali Image File(iso) -> Linux -> Version: _Debian 10.x 64-bit_ -> Vritual machine name: _KaliLinux_ -> Location: _"path-to-where-you-want"_ -> Maximum disk size: _"as-you-want"_ -> I prefer to select _"Store vritual disk as a single file"_ -> Customize Hardware: _"Memory for this virtual machine: 4GB"_
    3.  Play virtual machine -> Graphical Install: Follow [Kali Linux Installation document](https://www.kali.org/docs/installation/hard-disk-install/)

-   <h5>Option-2: Download and Extract Kali VMware Edition </h5>

    -   Download [_Kali Virtual Machines Edition_](https://www.kali.org/get-kali/#kali-virtual-machines)
        -   Follow [installation document](https://www.kali.org/docs/virtualization/)

-   Refer to [Kali Linux Documents](https://www.kali.org/docs/)

---

#### 2. Apache Web Server

```sh
# if Apache web service daemon not installed
sudo apt install apache2 -y
# Initiate Apache Web service
sudo /etc/init.d/apache2 start,  or service apache2 start
# Verify Apache Web server operation
sudo service apahce2 status
# Stop Apache Web service
sudo service apahce2 stop
# Restart Apache Web service
sudo service apahce2 restart
# Reload Apache Web service
udo service apahce2 reload
# Start Apaceh service at boot
sudo systemctl enable apahce2
#Stop Apaceh service at boot
sudo systemctl disable apahce2

```

-   <h5>Verify the current network status</h5>

    1. Verify the current network configuration

    ```sh
    ifconfig -y
    ```

    2.  Open a Web-browser and enter
        <em>"url(localhost), or ip-address</em> into address-bar"
    3.  Edit index.html file

    ```sh
    cd /var/www/html
    sudo mv index.html index_org.html
    # if gedit not installed
    sudo apt install gedit
    sudo gedit index.html

    ```

    ```html
    <html>
        <head>
            <title>Kali Linux Web Server</title>
        </head>
        <body>
            <h1>Hello, Kali Linux</h1>
        </body>
    </html>
    ```

    4.  Refresh Web browser

---

#### 3. Check Local DNS Server

-   Check DNS server status

    ```sh
    ifconfig
    hostname -f
    ping my-host-name

    # verify DNS server IP address
    cat /etc/resolv.conf or dig localhost(my-host-name)
    ping dns-server-ip

    ```

-   Host-name change (localhost)

    ```sh
    # verify the current host name
    hostnamectl
    # verify DNS server IP address
    sudo hostnamectl set-hostname samkali.edu
    # edit the /etc/hosts file
    sudo nano /etc/hosts

    ```

    ```sh
    # change 127.0.1.1 host name
    127.0.0.1       localhost
    127.0.1.1       samkali.edu

    ```

---

#### 4. Setup File Server

```sh
# Install vsftpd package if necessary
dpkg --list ftp
apt-get install vsftpd
# Configure and activate ftp service
sudo gedit /etc/vsftpd.conf
```

```html
# set configuration # local_enable=YES, anonymous_enable=NO, write_enable=YES,
chroot_list_enalbe=YES, chroot_list_file=/etc/vsftpd.chroot_list
```

```sh
sudo service vsftpd restart
nmap host-ip-address
netstat -nat | grep 21

```

---

#### 4. Setup SSH Server

```sh
# Install ssh package if necessary
dpkg --list ftp
apt-get install ssh
# Activate ftp service
sudo service ssh start
nmap host-ip-address
netstat -nat | grep 22

```

---

#### 5. Change DNS Configuration

```sh
# Verify the current dns configuration
cat /etc/resolv.conf
# Install and start the resolvconf if necessary
sudo apt install resolvconf
# Activate service
sudo systemctl enable resolvconf.service
sudo systemctl start resolvconf.service
sudo systemctl status resolvconf.service

```

---

<!--
#### 6. Install and Configure DNS Configuration

```sh
# Install Bind. All DNS configurations are stored under /etc/bind directory
sudo apt-get install bind9
cat /etc/bind/named.conf
# Configure Cache Nameserver

``` -->
