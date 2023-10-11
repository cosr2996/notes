#grep #strings 
#### Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

### Solution
```shell                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
private.zip  strings
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ strings  strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ 
```

### Flag
picoCTF{5tRIng5_1T_7f766a23}