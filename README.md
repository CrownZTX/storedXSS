# Stored XSS in Geeklog v2.2.2
Geeklog v2.2.2 is vulnerable to Stored Cross-Site Scripting (XSS) in public_html/admin/router.php

Vendor:https://github.com/Geeklog-Core/geeklog

## PoC
1. Log in to the Geeklog's admin account and Navigate to URL Routing and click an Edit button.

![Geeklog_route](https://github.com/CrownZTX/storedXSS/blob/main/images/geeklog_route.png)

2. Enter the payloads to the input areas of Rule and Route. Then click on SAVE. The payloads are
~~~
<script>alert('xss_rule');</script>
<script>alert('xss_route');</script>
~~~

![edit_routing](https://github.com/CrownZTX/storedXSS/blob/main/images/edit_routing.png)
3. We can observe the payloads getting triggered. Multiple visits to the routing manager page will still trigger payloads.

![xss_rule](https://github.com/CrownZTX/storedXSS/blob/main/images/xss_rule.png)

![xss_route](https://github.com/CrownZTX/storedXSS/blob/main/images/xss_route.png)

