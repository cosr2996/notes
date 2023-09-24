#### Description

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!

### Solution
```shell
┌──(kali㉿kali)-[~/Downloads]
└─$ ls 
archive.tar  -D.ltdis.x86_64.txt  -j.ltdis.x86_64.txt  ltdis.sh  private.zip  static
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ strings static|grep pico                 
picoCTF{d15a5m_t34s3r_f6c48608}

```

### Flag
picoCTF{d15a5m_t34s3r_f6c48608}