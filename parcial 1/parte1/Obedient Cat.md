#### Description

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag).

### Solution
```shell
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag   
--2023-09-24 13:39:42--  https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: ‘flag’

flag                         100%[=============================================>]      34  --.-KB/s    in 0s      

2023-09-24 13:39:43 (85.3 MB/s) - ‘flag’ saved [34/34]

                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ lss                                      
Command 'lss' not found, but there are 16 similar ones.
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ ls 
Desktop  Documents  Downloads  flag  hash.txt  home  key  Music  Pictures  Public  Templates  Videos
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cat flag                 
picoCTF{s4n1ty_v3r1f13d_2aa22101}
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ 

```

### Flag
picoCTF{s4n1ty_v3r1f13d_2aa22101}