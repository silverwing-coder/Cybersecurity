<h6>ver. Sep-2022</h6>

<h2> Steghide</h2>

-   Steganography tool for obfuscation, evasion, and covering attacker's tracks

-   Refer to

    [1. Stegehide: sourceforge](https://steghide.sourceforge.net/)

    [2. GitHub: steghide](https://github.com/StefanoDeVuono/steghide)

    [3. Kali: steghide](https://www.kali.org/tools/steghide/)

---

```sh

# Not a KaliLinux default tool
sudo apt install steghide

steghide --help

cat secret.txt
ls -l
steghide embed –ef secret.txt –cf image.jpg
> Enter passphrase: xxxx
> Renter passphrase: xxxx
ls-l
steghide extract –sf image.jpg –xf extracted_secret.txt
> Enter passphrase: xxxx
ls –l
diff secret.txt extracted_secret.txt

```
