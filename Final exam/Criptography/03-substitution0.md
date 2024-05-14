## Goal
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/152/message.txt).
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/substitution0]
└─$ wget https://artifacts.picoctf.net/c/152/message.txt 
--2024-05-05 03:24:48--  https://artifacts.picoctf.net/c/152/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.3, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 670 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[==================================>]     670  --.-KB/s    in 0s      

2024-05-05 03:24:49 (40.1 MB/s) - ‘message.txt’ saved [670/670]

                                                                                                    
┌──(kali㉿kali)-[~/picoCTF/Final_exam/substitution0]
└─$ cat message.txt 
DECKFMYIQJRWTZPXGNABUSOLVH 

Ifnfuxpz Wfyndzk dnpaf, oqbi d yndsf dzk abdbfwv dqn, dzk enpuyib tf bif effbwf
mnpt d ywdaa cdaf qz oiqci qb oda fzcwpafk. Qb oda d efdubqmuw acdndedfua, dzk, db
bidb bqtf, uzrzpoz bp zdbundwqaba—pm cpunaf d ynfdb xnqhf qz d acqfzbqmqc xpqzb
pm sqfo. Bifnf ofnf bop npuzk ewdcr axpba zfdn pzf flbnftqbv pm bif edcr, dzk d
wpzy pzf zfdn bif pbifn. Bif acdwfa ofnf flcffkqzywv idnk dzk ywpaav, oqbi dww bif
dxxfdndzcf pm eunzqaifk ypwk. Bif ofqyib pm bif qzafcb oda sfnv nftdnrdewf, dzk,
bdrqzy dww biqzya qzbp cpzaqkfndbqpz, Q cpuwk idnkwv ewdtf Juxqbfn mpn iqa pxqzqpz
nfaxfcbqzy qb.

Bif mwdy qa: xqcpCBM{5UE5717U710Z_3S0WU710Z_59533D2F}
````

+ Download the text file
+ Read its contents
+ I copied and pasted the contents of the file into a tool known as [quipquip3](https://www.quipqiup.com/) so that it would attempt to decipher the ciphertext.
	ABCDEFGHIJKLMNOPQRSTUVWXYZ Legrand stood up with a grave and stately air and brought me the beetle from a display case in which it was enclosed. It was a beautiful beetle, unknown at that time to naturalists, and certainly a great prize from a scientific point of view. It had two round black spots near one end of the back and a long one near the other. The scales were extremely hard and shiny, with all the appearance of burnished gold. The weight of the insect was very remarkable and, all things considered, I could hardly reproach Jupiter for his opinion of it. The flag is: picoCTF{5UB5717U710N_3V0LU710N_59533A2E}
## Notes

## References