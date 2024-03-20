## Goal

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:47967/](http://mercury.picoctf.net:47967/)
## Solution

+ I copied the challenge link, went to proxy ->intercept->intercept on, then clicked on a browser that opens burpsuite and pasted that link [pico challenge]().  
+ The buttons on the page I was switching between red and blue, uncheck the intercept option in burpsuite.  
+ In the proxy->history option select one of the records that burpsuite was capturing, in request it generated this:  
  
HEAD /index.php HTTP/1.1  
Host: [mercury.picoctf.net:47967](http://mercury.picoctf.net:47967/)  
Content-Length: 0  
Cache-Control: max-age=0  
Upgrade-Insecure-Requests: 1  
Origin: [http://mercury.picoctf.net:47967](http://mercury.picoctf.net:47967/)  
Content-Type: application/x-www-form-urlencoded  
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.6167.160 Safari/537.36  
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7  
Referer: [http://mercury.picoctf.net:47967/](http://mercury.picoctf.net:47967/)  
Accept-Encoding: gzip, deflate, br  
Accept-Language: en-US,en;q=0.9  
Connection: close  
  
+ Select this HEAD /index.php HTTP/1.1 and press ctr + r  
  
+ In the menu above in the repeater->inspector option there is a box where the request attributes are shown, change the value of the Method attribute to HEAD, in the center pane the flag will be displayed  
  
  
HTTP/1.1 200 OK  
flag: picoCTF{r3j3ct_th3_du4l1ty_cca66bd3}  
Content-type: text/html; charset=UTF-8  

## Notes

## Basic Burp Suite Documentation

**Introduction**

Burp Suite is an open-source web penetration testing tool. It's one of the most popular and comprehensive tools available, used by security professionals worldwide.

**Components of Burp Suite**

Burp Suite is made up of a suite of tools that can be used to test different aspects of a web application. Some of the most important tools include:

- **Proxy:** The Burp Suite proxy intercepts all HTTP traffic between your browser and the web application. This allows Burp Suite to view and modify HTTP requests and responses.
- **Scanner:** The Burp Suite scanner can automatically scan a web application for common vulnerabilities.
- **Intruder:** The Burp Suite intruder can be used to perform brute-force attacks and fuzzing against a web application.
- **Repeater:** The Burp Suite repeater can be used to manually send HTTP requests to a web application.
- **Sequencer:** The Burp Suite sequencer can be used to record and replay sequences of HTTP requests.

## References

- [The official Burp Suite documentation ](https://portswigger.net/burp/documentation)
- [The PortSwigger blog](https://portswigger.net/blog)
- [The Burp Suite user forum](https://forum.portswigger.net/)