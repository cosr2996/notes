#### Description

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 52682`

### Solution

```shell                             
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 52682
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ 
                                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ python                     
Python 3.11.5 (main, Aug 29 2023, 15:31:31) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x62)
'b'
>>> chr(0x64)
'd'
>>> chr(0x61)
'a'
>>> chr(0x36)
'6'
>>> chr(0x38)
'8'
>>> chr(0x66)
'f'
>>> chr(0x37)
'7'
>>> chr(0x35)
'5'
>>> 
KeyboardInterrupt
>>> 
****
```
### Flag
picoCTF{gl17ch_m3_n07_bda68f75}