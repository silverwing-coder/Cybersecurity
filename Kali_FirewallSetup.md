### Firewall Setup: IS-222 Lab. Session

**_School of Arts and Science, Carolina University_**

---

#### Linux Firewalls

1. IPTables(Linux firewall): Refer to [IPTables Tutorial](https://homes.di.unimi.it/sisop/qemu/iptables-tutorial.pdf), and [IPTables commands](https://johnnylinux.com/files/Documents/iptables.pdf)
    > - IPTables is default firewall application on Kali Linux
    >     - _sudo apt-get install kali-root-login_
    >     - _su_
2. UFW(Uncomplicated Firewall): Refer to [UFW commands](https://johnnylinux.com/files/Documents/UFW.pdf)
    > - **Option-1: UFW - command line configuration**
    >     - _sudo apt-get install kali-root-login_
    >     - _su_
    >     - _apt-get install ufw_
    >     - _ufw app list_
    >     - _ufw status_
    >     - _ufw status verbose_
    >     - _ufw enable_
    >     - _ufw status verbose_
    >     - _ufw allow 80/tcp_
    >     - _ufw status verbose_
    >     - _ufw allow 22/tcp_
    >     - _ufw status verbose_
    >     - _ufw status numbered_
    >     - _ufw deny from 192.168.31.1_
    >     - _ufw status numbered_
    >     - _ufw deny from 192.168.31.100/8 to 192.168.1.102 port25_
    >     - _ufw limit 80/tcp_
    >     - _ufw status numbered_
    >     - _ufw deny in on eth0 to any port 25 proto tcp_
    >     - _ufw delete number-to-delete_
    >     - _ufw status numbered_
    >     - _cat /etc/ufw/before.rules_
    > - **Option-2: GUFW - graphical user interface**
    >     - _apt-get install gufw_
    >     - _gufw_
    > - **Checking UFW logs**
    >     - _ufw logging on_
    >     - _ufw logging low/mdeium/high/full_
    >     - _ls /var/log/*ufw*_
    >     - _cat /var/log/ufw.log_
