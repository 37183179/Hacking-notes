## Goal

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:27177/](http://mercury.picoctf.net:27177/)
## Solution
+ Open burp suite, go to proxy and activate the interception, open the browser and copy the link of the challenge [challenge link](http://mercury.picoctf.net:27177/) in the browser, add to the cookies search the word "sugar" and click on search.
+ Go back to proxy->HTTP history and go to the query history section, click where the check appears in the history, below should appear this: 
		GET /check HTTP/1.1
		Host: mercury.picoctf.net:27177
		Cache-Control: max-age=0
		Upgrade-Insecure-Requests: 1
		User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.6167.160 Safari/537.36
		Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
		
		Referer: http://mercury.picoctf.net:27177/
		Accept-Encoding: gzip, deflate, br
		Accept-Language: en-US,en;q=0.9
		Cookie: name=7
		Connection: close

+ In that part we right click->send intruder, go to intruder->payloads and configure the following:
	Payload sets:
	+ PayloadType: Numbers
	Payload Options:
	+ Type: Secuential
	+ Start: 1
	+ A: 50
	+ Jump: 1
+ Start attack
+ You will have to analyse each request and see where the flag is in the code.
 picoCTF{3v3ry1_l0v3s_c00k135_064663be}

## Notes

### Basic Burp Suite Documentation

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