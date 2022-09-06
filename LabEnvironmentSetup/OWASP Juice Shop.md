<h6>ver. Aug-2022</h6>

<h2> OWASP <font color=blue>Juice Shop</font></h2>

<h3> Juice Shop Project Intro.</h3>

<i>Refer to https://owasp.org/www-project-juice-shop/</i>

<h3> Installation</h3>

<em>Refer to https://github.com/juice-shop/juice-shop_</em>

<h5> $1. Install Visual Studio Code: Can be applied to any applications on linux</h5>

1. Download image: file-name.dev for Kali-linux (https://code.visualstudio.com/download)
2. Go to te directory that contains the image

```sh
sudo apt install file-name.dev

```

<h5> $2. Update and upgrade Kali-linux</h5>

```sh
sudo apt update
sudo apt dist-upgrade
sudo apt autoremove

```

<h5> $3. Node.js install</h5>

1. Install by downloaded image: _Refer to $1_
2. Install by Shell command

```sh
sudo apt install nodejs
node -v

```

<h5> $4. NPM install</h5>

```sh
sudo apt install npm
```

<h5> $5. Deploy Juice Shop on Kali-linux (From sources)</h5>

1. Install Node.js
2. Copy sources from GitHub

```sh
git clone https://github.com/juice-shop/juice-shop.git --depth 1
cd juice-shop
npm install
npm start

```

3. Browse to _http://localhost:3000_

<h3> Web manual</h3>

<emp>Refer to https://pwning.owasp-juice.shop/</emp>
