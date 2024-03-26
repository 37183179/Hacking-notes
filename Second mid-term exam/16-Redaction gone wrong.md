## Goal
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Hints
How can you be sure of the redaction?
## Solution

+ I opened the file
+ And you find the password hidden in the text

```bash
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Redaction gone wrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf 
--2024-03-25 21:56:33--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_fo 100%[================>]  34.10K  --.-KB/s    in 0.04s   

2024-03-25 21:56:34 (796 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Redaction gone wrong]
└─$ file Financial_Report_for_ABC_Labs.pdf 
Financial_Report_for_ABC_Labs.pdf: PDF document, version 1.7, 1 page(s)
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Redaction gone wrong]
└─$ open Financial_Report_for_ABC_Labs.pdf 
````

+ Pdf text: Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.
Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.
## Notes

## References