#unzip #wget
#### Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip)

### Solution
```shell
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ wget https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip
--2023-09-24 13:54:07--  https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: ‘Addadshashanammu.zip’

Addadshashanammu.zip         100%[==============================================>]   4.41K  --.-KB/s    in 0s      

2023-09-24 13:54:07 (158 MB/s) - ‘Addadshashanammu.zip’ saved [4520/4520]

                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
Addadshashanammu.zip  archive.tar  private.zip
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
Addadshashanammu  Addadshashanammu.zip  archive.tar  private.zip
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Assurnabitashpi
cd: no such file or directory: Assurnabitashpi
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Addadshashanammu 
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu]
└─$ ls
Almurbalarammi
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu]
└─$ cd Almurbalarammi  
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu/Almurbalarammi]
└─$ ls
Ashalmimilkala
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu/Almurbalarammi]
└─$ cd Ashalmimilkala 
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ ls
Assurnabitashpi
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads/Addadshashanammu/Almurbalarammi/Ashalmimilkala]
└─$ cd Assurnabitashpi 
                                                                                                                    
┌──(kali㉿kali)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ ls
Maelkashishi
                                                                                                                    
┌──(kali㉿kali)-[~/…/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi]
└─$ cd Maelkashishi   
                                                                                                                    
┌──(kali㉿kali)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ ls
Onnissiralis
                                                                                                                    
┌──(kali㉿kali)-[~/…/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi]
└─$ cd Onnissiralis 
                                                                                                                    
┌──(kali㉿kali)-[~/…/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis]
└─$ ls
Ularradallaku
                                                                                                                    
┌──(kali㉿kali)-[~/…/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis]
└─$ cd Ularradallaku 
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ LS
LS: command not found
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ cat fang-of-haynekhtnamet 
 HH/lib64/ld-linux-x86-64.so.2GNUGNU_���
8#TT 1tt$D���o�N
�� ��0)@▒=      (;▒�                                                                                                                    .so.6puts__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls -la
total 20
drwxr-xr-x 2 kali kali 4096 Mar 15  2021 .
drwxr-xr-x 3 kali kali 4096 Mar 15  2021 ..
-rwxr-xr-x 1 kali kali 8320 Mar 15  2021 fang-of-haynekhtnamet
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=5fffe70019957f0a27a70bb886b2cfb9f9b21d6e, not stripped
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ chmod +x fang-of-haynekhtnamet
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}
                                                                                                                    
┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ 

```

### Flag
picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}