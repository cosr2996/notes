#python #crack #unicode 
#### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

### Solution

```shell
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
level2.flag.txt.enc  level2.py  private.zip
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ python          
Python 3.11.5 (main, Aug 29 2023, 15:31:31) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x33)
'3'
>>> chr(0x39)
'9'
>>> chr(0x63)
'c'
>>> chr(0x65)
'e'


┌──(kali㉿kali)-[~/Downloads]
└─$ python level2.py 
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```
### Flag
picoCTF{tr45h_51ng1ng_502ec42e}