## Goal
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)
## Hints
Look up the charAt() method online.
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ wget https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java
--2024-04-21 19:00:32--  https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2264 (2.2K) [application/octet-stream]
Saving to: ‘VaultDoor1.java’

VaultDoor1.java     100%[================>]   2.21K  --.-KB/s    in 0s      

2024-04-21 19:00:32 (79.9 MB/s) - ‘VaultDoor1.java’ saved [2264/2264]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ file VaultDoor1.java 
VaultDoor1.java: C++ source, ASCII text
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ cat VaultDoor1.java 
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
    }
}
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ nano vault-1-flag.txt 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ cat vault-1-flag.txt  
               password.charAt(00)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(04)  == 'r' &&
               password.charAt(02)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(03)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(01)  == '3' &&
               password.charAt(07)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(05)  == '4' &&
               password.charAt(09)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(08)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(06)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4'
               
vault-1-flag.txt  VaultDoor1.class  VaultDoor1.java
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ cat VaultDoor1Flag | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4                                                                                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ javac VaultDoor1.java                                                 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ java VaultDoor1      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4
Access denied!
                                                                                                                                                                                                                                 
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/vault-door-1]
└─$ java VaultDoor1      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
Access granted.
````
## Notes
**1. `cat VaultDoor1Flag`:**

This command utilizes the `cat` utility to concatenate and display the contents of the file named "VaultDoor1Flag".

**2. `sort`:**

The `sort` command sorts the lines of the input file (in this case, the output of the `cat` command) in alphabetical order.

**3. `awk '{print($3)}'`:**

This command employs the `awk` tool to process the lines sorted by the `sort` command. The code block within the curly braces `{}` specifies the action to be performed on each line. In this case, the action is to print only the third field of the current line.

**4. `tr -d "'" | tr -d "\n"`:**

This command utilizes the `tr` utility to remove two specific characters from the output of the `awk` command. The first invocation of `tr` removes single quotes (') from the output. The second invocation of `tr` removes newline characters (\n), resulting in a string of characters formed solely by the content of the third field of each original line, concatenated without spaces or line breaks.
## References
- `cat`: [https://man7.org/linux/man-pages/man1/cat.1.html](https://man7.org/linux/man-pages/man1/cat.1.html)
- `sort`: [https://man7.org/linux/man-pages/man1/sort.1.html](https://man7.org/linux/man-pages/man1/sort.1.html)
- `awk`: [https://www.gnu.org/s/gawk/manual/gawk.html](https://www.gnu.org/s/gawk/manual/gawk.html)
- `tr`: [https://linuxcommand.org/lc3_man_pages/tr1.html](https://linuxcommand.org/lc3_man_pages/tr1.html)