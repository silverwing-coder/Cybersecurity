<h6>ver. Sep-2022</h6>
<h2> Recon-ng</h2>

-   Full featured Web Reconnaissance Framework written in Python
-   Used for automated information gathering of OSINT (detailed searches of public records)
-   Refer to

    [1. GitHub: Recon-ng](https://github.com/lanmaster53/recon-ng)

    [2. Kali-Linux: Recon-ng](https://www.kali.org/tools/recon-ng/)

    [3. Geeksforgeeks Tutorial: Recon-ng](https://www.geeksforgeeks.org/recon-ng-installation-on-kali-linux/#:~:text=Recon%2Dng%20is%20a%20Web,we%20can%20gather%20all%20information)

    [4. Hackertarget Tutorial: Recon-ng](https://hackertarget.com/recon-ng-tutorial/)

---

```sh
# Installed by default on Kali Linux
sudo apt update & apt install recon-ng

recon-ng -h
recon-ng --version

# load/create workspace for each reconnaissance project
recon-ng -w workspace-name

# if default workspace is used
recon-ng
> help
# search markets
> marketplace search
# search modules installed
> modules search
# hackertarget module: gather some subdomains
> marketplace install hackertarget
> modules load hackertarget
> show options
> options set SOURCE carolinau.edu
> info
> input
> run
> show hosts

# add API keys to Recon-ng
> keys add shodan_api shodan-api-key
> keys list

# use recon/hosts-hosts/resolve module
> marketplace install resolve
> modules search
> modules load recon/hosts-hosts/resolve
> options set SOURCE h4cker.org
> info
> run
> back

# use recon/domains-hosts/shodan_hostname module
> marketplace install shodan_hostname
> modules search
> modules load recon/domains-hosts/shodan_hostname
> options set SOURCE example.org
> info
> run
> back


# use recon/domains-hosts/shodan_hostname


# check api database: keys.db
ls ~/.recon-ng


```
