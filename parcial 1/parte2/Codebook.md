#python 
#### Description

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

### Solution

```shell
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
archive.tar  codebook.txt  code.py  private.zip
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat codebook.txt 
azbycxdwevfugthsirjqkplomn
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python code.py            
picoCTF{c0d3b00k_455157_197a982c}
                                                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ 
```

### Flag
picoCTF{c0d3b00k_455157_197a982c}
