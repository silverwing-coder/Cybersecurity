<h6>ver. Sep-2022</h6>
<h2> Burp Suite</h2>

-   An integrated, automated tool for pen tesing based on Web proxy technology
-   Refer to

    [1. PortSwigger Burp Suite](https://portswigger.net/)

    [2. Kali: Burpsuite](https://www.kali.org/tools/burpsuite/)

---

```sh

# KaliLinux default
sudo apt install burpsuite

# invoke GUI Burpsuite
burpsuite

```

<h4> Tutorials </h4>

[1. PortSwigger Tutorials](https://portswigger.net/burp/documentation/desktop): Professional & Commuinity Version

```sh

### CompTIA PenTest Reference

## Browser Setup (FireFox)
#   Firefox ->
#       Settings ->
#           Network Settings ->
#               Settings ->
#                   Manual proxy configuration
#                   {HTTP proxy 127.0.0.1, Port: 8080, Also use this proxy for HTTPS}


## Burp Suite Execution
#   1. Select project - Temporary project
#   2. Selcet configuration- Use Burp defaults
#   3. Set Proxy Listeners
#       Proxy ->
#        Options ->
#          Proxy Listener: Add 127.0.0.1:8080


# 1. Target
#   - Scope: Include in scope / Exclude from scope
# 2. Proxy
#   - Intercept
#   - HTTP history
#   - WebSocket history
#   - Options
# 3. Intruder: Intrude with tools and payloads
# 4. Repeater: Repeat sending wito different values
# 5. Sequencer: Randomization verification
# 6. Decoder
# 7. Comparer, etc.

```
