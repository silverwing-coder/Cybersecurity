<h6>Ver. Aug-2021.</h6>

### Firewall Setup

**_School of Arts and Science, Carolina University_**

---

#### Linux Firewalls

1. IPTables(Linux firewall): Refer to [IPTables Tutorial](https://homes.di.unimi.it/sisop/qemu/iptables-tutorial.pdf), and [IPTables commands](https://johnnylinux.com/files/Documents/iptables.pdf)

    - IPTables is default firewall application on Kali Linux

    ```sh
    sudo apt-get install kali-root-login
    su
    ```

2. UFW(Uncomplicated Firewall): Refer to [UFW commands](https://johnnylinux.com/files/Documents/UFW.pdf)

    - **Option-1: UFW - command line configuration**

    ```sh
    sudo apt-get install kali-root-login
    su
    apt-get install ufw
    ufw app list
    ufw status
    ufw status verbose
    ufw enable
    ufw status verbose
    ufw allow 80/tcp
    ufw status verbose
    ufw allow 22/tcp
    ufw status verbose
    ufw status numbered
    ufw deny from 192.168.31.1
    ufw status numbered
    ufw deny from 192.168.31.100/8 to 192.168.1.102 port25
    ufw limit 80/tcp
    ufw status numbered
    ufw deny in on eth0 to any port 25 proto tcp
    ufw delete number-to-delete
    ufw status numbered
    cat /etc/ufw/before.rules

    ```

    - **Option-2: GUFW - graphical user interface**

    ```sh
    apt-get install gufw
    gufw

    ```

    - **Checking UFW logs**

    ```sh
    ufw logging on
    ufw logging low/mdeium/high/full
    ls /var/log/ufw
    cat /var/log/ufw.log

    ```
