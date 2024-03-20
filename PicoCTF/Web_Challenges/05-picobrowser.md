
## Goal

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921
## Solution

```bash
 curl http://jupiter.challenges.picoctf.org:28921/flag -H "User-Agent: picobrowser" | grep picoCTF
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   1035      0  0:00:02  0:00:02 --:--:--  1035
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
````


## Notes

Curl Command
+ Purpose: curl is a powerful command-line tool for transferring data to and from servers using URLs. *It's versatile and widely used for various tasks, including:
	+ Downloading files
	+ Uploading files
	+ Posting data to web forms
	+ Interacting with web APIs
	
 User Agent
	+ What it is: A user agent is a string sent by a web browser (or other client) in the HTTP request header. It identifies the browser, operating system, device, and other information to the website.
	+ Purpose: Websites use user agents to:
		 + Tailor content and functionality to specific browsers and devices
		 + Detect and block malicious bots

## References

[Curl](https://curl.se/)
[User-agent](https://developer.mozilla.org/es/docs/Web/HTTP/Headers/User-Agent)
[Http headers](https://developer.mozilla.org/es/docs/Web/HTTP/Headers)

