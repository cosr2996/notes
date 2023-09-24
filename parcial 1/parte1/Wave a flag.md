#### Description

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...

### Solution
```shell
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm                
--2023-09-24 13:58:32--  https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: ‘warm’

warm                         100%[==============================================>]  10.68K  --.-KB/s    in 0s      

2023-09-24 13:58:38 (381 MB/s) - ‘warm’ saved [10936/10936]

                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
archive.tar  private.zip  warm
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x warm                 
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm                 
Hello user! Pass me a -h to learn what I can do!
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ./warm -h    
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

### Flag
picoCTF{b1scu1ts_4nd_gr4vy_30e77291}