<h6><em>[Under costruction]</em> Ver. Nov-2022 </h6>

### Metasploitable-2

**_School of Arts and Sciences, Carolina University_**

---

<h4> 1. Install Metasploitable-2 in VurtualBox </h4>

-   Download <b>Mestasplotable-2 Virtual Machine Image</b> from [RAPID7](https://docs.rapid7.com/metasploit/metasploitable-2/) or [vulnhub](https://www.vulnhub.com/entry/metasploitable-2,29/)
-   Extract the downloaded zip file
-   Import Metasplitable-2 Virtual Machine into Virtualbox (Search YouTube tutorials)
-   <u><b>[WARNING]: Do not expose the exploitable-2 to the Ineternet. </b></u>

<h4> 2. Metasploitable-2 management </h4>

-   root user id/password: msfadmin:msfadmin
    -   SSH is open

```sh

$ ifconfig

# SSH login: OpenSSH since 7.0 doesn't accept hostkey ssh-dss and your must add it,
# similarly since 8.8 does not use client ssh-rsa.
ssh -v -oHostKeyAlgorithms=+ssh-rsa username@ipaddress

```

-   Refer to [Metasplotable-2 Exploitability Gudide](https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/)
