#python  #crack
#### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

### Solution

```shell
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
level1.flag.txt.enc  level1.py  private.zip
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ file level1.flag.txt.enc 
level1.flag.txt.enc: data
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level1.               
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level1.py 
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ python level1.py        
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

### Flag
picoCTF{545h_r1ng1ng_56891419}