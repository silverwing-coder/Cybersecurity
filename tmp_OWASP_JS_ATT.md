<h5><em>ver. Sep-2022</em></h5>
<h3> OWASP Juice Shop Vulnerabilties </h3>

<h4> Directory Traversal </h4>

1. owasp-js-ip-address:3000/#/score-board
    - Check the code by inspector: find "path"

<h4> XSS </h4>

1. Search 
    - "\<h2> OWASP"
    - "\<iframe src="javascript:alert(`xss`)">
    - "\<iframe src="javascript:\<a href="google.com">Google\</a>">

2. Cowasp-js-ip-address:3000/#/score-board
    - Check the code by inspector: find "path"