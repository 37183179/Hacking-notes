## Goal
[crackme.py](https://mercury.picoctf.net/static/be2ba466c6154e42c756bf737ddcecc3/crackme.py)
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/crackme]
└─$ wget https://mercury.picoctf.net/static/be2ba466c6154e42c756bf737ddcecc3/crackme.py
--2024-05-10 21:42:16--  https://mercury.picoctf.net/static/be2ba466c6154e42c756bf737ddcecc3/crackme.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1463 (1.4K) [application/octet-stream]
Saving to: ‘crackme.py’

crackme.py                                                 100%[========================================================================================================================================>]   1.43K  --.-KB/s    in 0s      

2024-05-10 21:42:16 (50.4 MB/s) - ‘crackme.py’ saved [1463/1463]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/crackme]
└─$ cat crackme.py 
# Hiding this really important number in an obscure piece of code is brilliant!
# AND it's encrypted!
# We want our biggest client to know his information is safe with us.
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE0cdhb52g2N"

# Reference alphabet
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"



def decode_secret(secret):
    """ROT47 decode

    NOTE: encode and decode are the same operation in the ROT cipher family.
    """

    # Encryption key
    rotate_const = 47

    # Storage for decoded secret
    decoded = ""

    # decode loop
    for c in secret:
        index = alphabet.find(c)
        original_index = (index + rotate_const) % len(alphabet)
        decoded = decoded + alphabet[original_index]

    print(decoded)



def choose_greatest():
    """Echo the largest of the two numbers given by the user to the program

    Warning: this function was written quickly and needs proper error handling
    """

    user_value_1 = input("What's your first number? ")
    user_value_2 = input("What's your second number? ")
    greatest_value = user_value_1 # need a value to return if 1 & 2 are equal

    if user_value_1 > user_value_2:
        greatest_value = user_value_1
    elif user_value_1 < user_value_2:
        greatest_value = user_value_2

    print( "The number with largest positive magnitude is "
        + str(greatest_value) )



choose_greatest()
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/crackme]
└─$ cat crackme.py
# Hiding this really important number in an obscure piece of code is brilliant!
# AND it's encrypted!
# We want our biggest client to know his information is safe with us.
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE0cdhb52g2N"

# Reference alphabet
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"



def decode_secret(secret):
    """ROT47 decode

    NOTE: encode and decode are the same operation in the ROT cipher family.
    """

    # Encryption key
    rotate_const = 47

    # Storage for decoded secret
    decoded = ""

    # decode loop
    for c in secret:
        index = alphabet.find(c)
        original_index = (index + rotate_const) % len(alphabet)
        decoded = decoded + alphabet[original_index]

    print(decoded)



def choose_greatest():
    """Echo the largest of the two numbers given by the user to the program

    Warning: this function was written quickly and needs proper error handling
    """

    user_value_1 = input("What's your first number? ")
    user_value_2 = input("What's your second number? ")
    greatest_value = user_value_1 # need a value to return if 1 & 2 are equal

    if user_value_1 > user_value_2:
        greatest_value = user_value_1
    elif user_value_1 < user_value_2:
        greatest_value = user_value_2

    print( "The number with largest positive magnitude is "
        + str(greatest_value) )



#choose_greatest()
decode_secret(bezos_cc_secret)
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/crackme]
└─$ python3 crackme.py 
picoCTF{1|\/|_4_p34|\|ut_4593da8a}

````
## Notes

## References