### Setup Computer Network Infrastructure: MG-245 Lab. Session

**_School of Arts and Science, Carolina University_**

---

#### 1. Install Kali Linux on a Virtual Machine

> -   Download and Install VMware and Kali Linux separately
>     -   [Download _VMware Workstation Player(Free Edition preferred)_](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html)
>         -   Install VMware for non-commercial use
>     -   [Download _Kali Bare Metal Installer Edition_](https://www.kali.org/get-kali/#kali-bare-metal)(kali-linux-2021xxxxxx.iso)
>         -   Refer to [installation document](https://www.kali.org/docs/installation/hard-disk-install/)
>         -   Thre is no problem to setup with default optionss
>         -   Your PC/Laptop spec. will affect the performance of virtual machine
> -   Procedure
>     1. Open VMware Workstation Player
>     2. Create a New Virtual Machine -> Installer disc Image file(iso) -> Select Downloaded Kali Image File(iso) -> Linux -> Version: _Debian 10.x 64-bit_ -> Vritual machine name: _KaliLinux_ -> Location: _"path-to-where-you-want"_ -> Maximum disk size: _"as-you-want"_ -> I prefer to select _"Store vritual disk as a single file"_ -> Customize Hardware: _"Memory for this virtual machine: 4GB"_
>     3. Play virtual machine -> Graphical Install: Follow [Kali Linux Installation document](https://www.kali.org/docs/installation/hard-disk-install/)
> -   Option-2: Download and Install Kali inside VMware
>     -   [Download _Kali Virtual Machines Edition_](https://www.kali.org/get-kali/#kali-virtual-machines)
>         -   Follow [installation document](https://www.kali.org/docs/virtualization/)
> -   Refer to [Kali Linux Documents](https://www.kali.org/docs/)

#### 2. Setup Apache Web Server

> -   By default, Apache web service demon is installed. If not installed
>     -   _sudo apt install apache2 -y_
> -   Initiate Apache Web service
>     -   _sudo /etc/init.d/apache2 start or service apache2 start_
> -   Verify Apache Web server operation
>     -   _sudo service apahce2 status_
> -   Stop Apache Web service
>     -   _sudo service apahce2 stop_
> -   Restart Apache Web service
>     -   _sudo service apahce2 restart_
> -   Reload Apache Web service
>     -   _sudo service apahce2 reload_
> -   Start Apaceh service at boot
>     -   _sudo systemctl enable apahce2_
> -   Stop Apaceh service at boot
>     -   _sudo systemctl disable apahce2_
> -   Check the current network status: IP address, etc.
>     1. Open a Terminal
>         - _ifconfig_
>     2. Open a Web browser and enter _url(localhost)_ or _ip address_ into _address-bar_
>     3. Edit index.html file - _cd /var/www/html_ - _sudo mv index.html index_org.html_ - _sudo apt install gedit_ **(If gedit is not installed)** - _sudo gedit index.html_ > `<html>` > `<head><title>Kali Linux Web Server</title></head>` > `<body><h1>Hello, Kali Linux</h1></body>` > `</html>`
>     4. Refresh Web browser

#### 3. Check Kali Linux Local DNS Server

> -   Check DNS server status
>     -   _ifconfig_
>     -   _hostname -f_
>     -   _ping my-host-name_
>     -   _ping dns-host-ip_

#### 4. Setup Kali Linux File Server

> -   Install vsftpd package if necessary
>     -   _dpkg --list *ftp*_
>     -   _apt-get install vsftpd_
> -   Setup and activate ftp service
>     -   _sudo gedit /etc/vsftpd.conf_ > `local_enable=YES` > `anonymous_enable=NO` > `write_enable=YES` > `chroot_list_enalbe=YES` > `chroot_list_file=/etc/vsftpd.chroot_list`
>     -   _sudo service vsftpd restart_
>     -   _nmap host-ip-address_
>     -   _netstat -nat | grep 21_

#### 4. Setup Kali Linux SSH Server

> -   Install ssh package if necessary
>     -   _dpkg --list *ftp*_
>     -   _apt-get install ssh_
> -   Activate ssh service
>     -   _sudo service ssh start_
>     -   _nmap host-ip-address_
>     -   _netstat -nat | grep 22_
