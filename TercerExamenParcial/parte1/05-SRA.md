# SRA

## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/sra]
└─$ cat chal.py
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
    
┌──(kali㉿kali)-[~/retos/3exa/sra]
└─$ nano sra.py

  GNU nano 7.2
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

#function to generate all the sub lists
def sub_lists (l):
    #initializing empty list
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
        #Generating sub list
        comb += [list(j) for j in combinations(l, i)]
    #Returning list
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
   #this is dangerous, but I'm trusting me
   return(eval(input()))


#connect to the server
r = remote('saturn.picoctf.net', 64826)
#get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
#get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
#since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
   #multiply them together to get p-1
   for k in l:
      product = product * k
   #if the right length and adding 1 yields a prime, then maybe
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
#try all possible prime pairs
for p in primelist:
   for q in primelist:
      n=p*q
      #decode with this possible n
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
         #see if it corresponds to text and if so, try it
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue


┌──(kali㉿kali)-[~/retos/3exa/sra]
└─$ python3 sra.py
[+] Opening connection to saturn.picoctf.net on port 64826: Done
/home/kali/retos/3exa/sra/sra.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/retos/3exa/sra/sra.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 7751342043660706010368461257849343290960798865544663012987339539238604034841
d= 60179527833503018417327388272002507904599563312546171045397995540632540476865
/home/kali/retos/3exa/sra/sra.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  3943985715624287318016385045182228360543741580814338411802248433746434805232301504
[2, 2, 2, 2, 2, 2, 3, 3, 67, 97, 109, 6199, 13591, 61343, 7027566050168519818843321027, 266131828943727714081929542132781]
{320051734278700611321212958946135227287, 281230615558689156737382417376805580049, 192408423130930109919987521740727443609}
dThBnHbSvPtazOc9
/home/kali/retos/3exa/sra/sra.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> dThBnHbSvPtazOc9\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}\r\n'
dThBnHbSvPtazOc9
[*] Closed connection to saturn.picoctf.net port 64826

picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}
```
## Notas adicionales

## Referencias
