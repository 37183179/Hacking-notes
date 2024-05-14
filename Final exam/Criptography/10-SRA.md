## Goal
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/SRA]
└─$ nc saturn.picoctf.net 65186
anger = 34592353963944480990016079890757932862511081231405468446478948837216406562209
envy = 31072099274404127142339301836653001800309653275322527427987249848074902143941
vainglory?
> AZm5qmkPDRs0vW1a
AZm5qmkPDRs0vW1a
Conquered!
picoCTF{7h053_51n5_4r3_n0_m0r3_ba95c657}

````


```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/SRA]
└─$ nano  chal2.py
┌──(kali㉿kali)-[~/picoCTF/Final_exam/SRA]
└─$ cat  chal2.py
# Importing necessary modules
from Crypto.Util.number import getPrime, isPrime, long_to_bytes
import itertools
import math
import string
import primefac  # Make sure this module is correctly installed

#====================================
# Retrieving provided information
#====================================

# Encrypted message
C = int(input("What is 'anger'? > ").strip())

# Decryption exponent
d = int(input("What is 'envy'? > ").strip())

# Encryption exponent
e = 65537  # sample value, adjust as needed


#====================================
# Decomposition into prime factors
#====================================

# Calculating (d * e) - 1
d_e_minus_1 = (d * e) - 1

# Factoring (d * e) - 1 to obtain prime factors
prime_factors = list(primefac.primefac(d_e_minus_1))
print(f"{prime_factors = }")


#====================================
# Identification of eligible prime factor combinations
#====================================

# 1. Determining all possible combinations of prime factors
def define_combinations(elements:[], combination_size:int) -> ():
    return set(itertools.combinations(elements, combination_size))

def define_all_combinations(elements:[]) -> ():
    all_combinations = set()
    for combination_size in range(2, len(prime_factors)-1):
        combinations = define_combinations(elements, combination_size)
        all_combinations |= combinations
    return all_combinations

all_combinations_of_prime_factors = define_all_combinations(prime_factors)


# 2. Retaining only combinations for which the product + 1 is a 128-bit prime number
max_prime = 2**129
min_prime = 2**127

list_of_prime_factors_p = set()
for factors in all_combinations_of_prime_factors:
    possible_p = math.prod(factors) + 1
    if isPrime(possible_p):
        if min_prime < possible_p < max_prime:
            list_of_prime_factors_p.add(factors)


# 3. Discarding combinations that are too large
min_size_prime_factors_p = min(len(prime_factors_p) for prime_factors_p in list_of_prime_factors_p)
max_size_prime_factors_p = len(prime_factors) - min_size_prime_factors_p

list_of_prime_factors_p = set(factors for factors in list_of_prime_factors_p if min_size_prime_factors_p <= len(factors) <= max_size_prime_factors_p)


#====================================
# Identification of eligible encryption modules
#====================================

modules = []
for factors_p in list_of_prime_factors_p:
    # 1. Determining the remaining factors (i.e., prime_factors - factors_p)
    factors_p_complement = prime_factors[:]
    for factor in factors_p:
        factors_p_complement.remove(factor)
    
    # 2. Finding complementary factors_q
    for factors_q in list_of_prime_factors_p:
        # Checking if all factors of q are in the remaining factors
        is_candidate = True
        for factor in factors_q:
            if not factor in factors_p_complement:
                # If not, factors of p and q overlap => cannot be paired
                is_candidate = False
                break
        if is_candidate:
            # If yes, factors p and q are disjoint => can be paired
            p = math.prod(factors_p) + 1
            q = math.prod(factors_q) + 1
            n = p * q
            modules.append(n)


#====================================
# Decryption
#====================================

# Allowed characters for the plaintext message: alphanumeric
accepted_characters_code = [ord(c) for c in string.ascii_letters + string.digits]

for n in modules:
    M = pow(C, d, n)
    M = long_to_bytes(M)
    if all(character in accepted_characters_code for character in M):
        # Only retaining plaintext messages containing allowed characters
        print(f"Possible vainglory: {M.decode()}")


        
┌──(kali㉿kali)-[~/picoCTF/Final_exam/SRA]
└─$ python3 chal2.py
anger ? > 34592353963944480990016079890757932862511081231405468446478948837216406562209
envy ? > 31072099274404127142339301836653001800309653275322527427987249848074902143941

prime_factors = [2, 2, 3, 3, 3, 7, 89, 967, 2267, 714529, 11433463, 95489239, 16451812762981, 861308459154163, 1248943532186999435999]
possible vainglory: AZm5qmkPDRs0vW1a
possible vainglory: AZm5qmkPDRs0vW1a


````
## Notes

## References
[code references](https://github.com/philippebaye/picoCTF-2023-writeup/tree/main/Cryptography/SRA)
