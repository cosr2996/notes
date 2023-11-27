#### Description
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt)


### Solution
```python
def main():
    f = open("message.txt", "r", encoding="UTF-8")
    txt = f.read()

    n=3
    txt3gram = [txt[i:i+n] for i in range(0, len(txt), n)]
    decode_lst = []

    for i in range(len(txt3gram)):
        decode_lst.append(txt3gram[i][2]+txt3gram[i][0]+txt3gram[i][1])

    print(''.join(decode_lst))


if __name__ == '__main__':
    main()
```


### Flag
picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}