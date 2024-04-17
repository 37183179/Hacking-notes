## Goal
How about we take you on an adventure on exploring certificate signing requests. Take a look at this CSR file [here](https://artifacts.picoctf.net/c/424/readmycert.csr).
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/ReadMyCert]
└─$ wget https://artifacts.picoctf.net/c/424/readmycert.csr
--2024-04-16 22:39:11--  https://artifacts.picoctf.net/c/424/readmycert.csr
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 997 [application/octet-stream]
Saving to: ‘readmycert.csr’

readmycert.csr             100%[========================================>]     997  --.-KB/s    in 0s      

2024-04-16 22:39:12 (23.9 MB/s) - ‘readmycert.csr’ saved [997/997]

┌──(kali㉿kali)-[~/picoCTF/Criptography/ReadMyCert]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF81YWVi
MGQ0Zn0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAMCkf11rmV8rgqPvC2ZiPA6W+5RfOTwU6u3WpGvLA+2YFzocBPut
aATTxTPB+uaN2ZN3Z5J2CTFGmPzI4sUQfSqhZGuAqbfMyDDR8pRswmIYVJ6s0Apc
Toi7H8m3IShSbeE0pZUSIJpbK1a7V6lJqgwFMDI1qrgNhGgZaMA/l+d2J0vC3EYd
AijwSs8APcp6woWbFGYwdw5KaBsjn23oVz2G4h3/TmdB5g5e6Oq+kgi38NEpRDS0
ylXo9mUko3FqS4I6y9gOtDEI4uZaCJZuXHDmBpqZ04MfXbIVlHjF9NMOjDvXLonN
650oaANBm4bhBlgid0Fx48Z36tbtAVivZEcCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAHZx6h9r
G/SE7RCoX6ndk5BOJprRiHpxOqPLAWcDyKHfStln0/HcQZzIrRVRsmoHiOmch+md
PBA1b+M5aj+3BWtPR9jOY4vht+ZmHAKa0WfQxwb2dBxsRPKTTDea0wN2u8BHLlSM
PbWPNuz+TKySL41xfwFuM4VN/ywn58GTvdb7HXgwNZCGgo2N1WhRq/dBMiagXMah
yb6gX4erugCu61T5tyD80hgsNBjaqyIdy/whRfC/Pmn3QHmdkqB5ZCPezwb2OLm4
5RDGv3WOB5q0BofoUGhVq757QE8qhL3oTvV2WlLoi3YWaZkJMCeR3vnH92cKC1Ov
FxdQuLOH8GMvl7U=
-----END CERTIFICATE REQUEST-----
````

+ Download the certificate  
+ I read the contents of the certificate  
+ I found a page to decode the .csr certificates  [decoder csr](https://www.sslshopper.com/csr-decoder.html)  
+ Copy and paste the certificate in the page  
+ I got this information:
		CSR Information:
		Common Name: picoCTF{read_mycert_5aeb0d4f}
		Key Size: 2048 bit}

##### **Key Size:** 2048 bit
## Notes
### Certificate signing request
In [public key infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure "Public key infrastructure") (PKI) systems, a **certificate signing request** (**CSR** or **certification request**) is a message sent from an applicant to a [certificate authority](https://en.wikipedia.org/wiki/Certificate_authority "Certificate authority") of the [public key infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure "Public key infrastructure") (PKI) in order to apply for a [digital identity certificate](https://en.wikipedia.org/wiki/Public_key_certificate "Public key certificate"). The CSR usually contains the public key for which the certificate should be issued, identifying information (such as a domain name) and a proof of authenticity including integrity protection.
## References
[Certificate signing request](https://en.wikipedia.org/wiki/Certificate_signing_request)