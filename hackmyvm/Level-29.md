### Level Goat
La usuaria celeste tiene acceso al mysql, pero para que?

### User
**celeste**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
celeste@venus:~$ mysql -p
Enter password: 
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 67
Server version: 10.11.3-MariaDB-1 Debian 12

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases
    -> ;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| venus              |
+--------------------+
2 rows in set (0.002 sec)

MariaDB [(none)]> use venus;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
MariaDB [venus]> show tables;
+-----------------+
| Tables_in_venus |
+-----------------+
| people          |
+-----------------+
1 row in set (0.001 sec)

MariaDB [venus]> salect * from people
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'salect * from people' at line 1
MariaDB [venus]> select * from people;
+-----------+---------------+--------------------------------+
| id_people | uzer          | pazz                           |
+-----------+---------------+--------------------------------+
|         1 | nuna          | ixpfdsvcxeqdW                  |
|         2 | nona          | ixpvcxvcxeqdW                  |
|         3 | manue         | ixpfdsfdseqdW                  |
|         4 | samoa         | ixperrewrweqdW                 |
|         5 | dsaewq        | ixpefdsfsqdW                   |
|         6 | fdsfewrew     | ixpedvcxv4qdW                  |
|         7 | koiuoiudsadas | ixpredsfdeqdW                  |
|         8 | vcxfdsfew     | ixp342432eqdW                  |
|         9 | dasd          | ixpeiuyiuyqdW                  |
|        10 | helen         | uytuytjhgixpeqdW               |
|        11 | tudou         | ijhgjghxpeqfdfsfddW            |
|        12 | fdsoiurew     | ixpfdsfsdsvcxvcxeqdW           |
|        13 | inan          | imbnmnbxpeqdW                  |
|        14 | zkret         | ixpeqkjhkhjkdW                 |
|        15 | cjhcx         | i432423xpeqdW                  |
|        16 | sfdfdsml      | ixpeqdsfsdfdsfW                |
|        17 | svcxvcxml     | 432423ixpeqdW                  |
|        18 | xml           | ixpejhgjhgqdW                  |
|        19 | pdf           | ixperewrewrewqdW               |
|        20 | txt           | ixpeuytuytqdW                  |
|        21 | vcxvcx        | ixpefdsfdsfdfdsqdW             |
|        22 | dsadsa        | ixpeqdjhkjhW                   |
|        23 | lel           | ixpvcxvcxvcxeqdW               |
|        24 | lul           | ixpeqdmnbmnbmnbmW              |
|        25 | dog           | ixperewrewrewqdW               |
|        26 | cat           | ixvcxvdsfsdvpeqdW              |
|        27 | pet           | ixiufohsyuoirewpeqdW           |
|        28 | pzzz          | ixvcxvcxvpeqdW                 |
|        29 | ls            | ixpehgfdhdhqdW                 |
|        30 | vi            | ixpetrvvrqdW                   |
|        31 | tmux          | iuovcxoiujvcxixpeqdW           |
|        32 | screen        | ixpeqrewregfdgdW               |
|        33 | yes           | ixpebvcgdfgqdW                 |
|        34 | nop           | ixpefdsqdW                     |
|        35 | haha          | 8===xKmPDsJSKpHLzkqKXyjx===D~~ |
|        36 | love          | ixpegfdgqdW                    |
|        37 | dsadsa        | fdsvcxvcxixpeqdW               |
|        38 | d4t4          | erwerewreixpeqdW               |
|        39 | nna           | gdfgdixpeqdW                   |
|        40 | nin           | aaafdixpeqdW                   |
|        41 | tre           | fdsafixpeqdW                   |
|        42 | tfas          | igfdgfdgxpeqdW                 |
|        43 | zcxc          | ixfdgdfgpeqdW                  |
|        44 | yuio          | ixpgbvcbvcbeqdW                |
|        45 | jhgyurtrt     | treterterixpeqdW               |
|        46 | lodsa         | itreterxpeqdW                  |
|        47 | zarah         | ixpvcbvcbeqdW                  |
|        48 | zkkad         | ixpedfgvbcxbvcqdW              |
|        49 | bvher         | vcxvcxgfdgfdixpeqdW            |
|        50 | dsadsa        | ixpeqergdfwer32dW              |
|        51 | ch4rm         | ixpeewf23qdW                   |
|        52 | Aza           | ixpjhgjgheqdW                  |
|        53 | avij          | ixpegfdgdfgqdW                 |
|        54 | crom          | ixpefdbvvcbrqdW                |
|        55 | bubu          | ixpetretretqdW                 |
|        56 | bebe          | ixpeghfgfdqdW                  |
|        57 | baba          | ixpeffesfqdW                   |
|        58 | bael          | ixpesdvsdvsdqdW                |
|        59 | vaze          | ixpe23r23rf23qdW               |
|        60 | upper         | ixpe43r43rqdW                  |
|        61 | loz           | ixpeqddfsdW                    |
|        62 | mind          | ixpfsdfsdfsdeqdW               |
|        63 | mymy          | ixpevcxvqdW                    |
|        64 | ina           | ixpee23e32rqdW                 |
|        65 | ein           | ixpejytjytjhgjqdW              |
|        66 | n1n4          | ixpehgjghjhghgqdW              |
|        67 | where         | ixljkgjgpeqdW                  |
|        68 | you           | ixpeqdhggjhgjW                 |
|        69 | are           | ixVCXVCXVCXVCXdW               |
|        70 | what          | ixpeqhgjggdW                   |
|        71 | dsaqqqqqq     | ixpeqVCXVCXdW                  |
|        72 | h0j3n         | ixpemnbmbnmghqdW               |
|        73 | nana          | ixpeqVSDFWCdW                  |
|        74 | nina          | ixpeqdWuvC5N9kG                |
|        75 | nunu          | ixpeSFDSFDSVCXqdW              |
|        76 | fdse          | ixpeDFSWEF2qdW                 |
|        77 | dsar          | ixpeF43F3F34qdW                |
|        78 | yop           | ixpeqdWCSDFDSFD                |
|        79 | loco          | ixpeF43F34F3qdW                |
|        80 | zaza          | ixpeYUTHNYGTHYTqdW             |
|        81 | jhon          | ixpeFDSJYTUJTYqdW              |
|        82 | tell          | ixpeHYTTqdW                    |
|        83 | ma            | uyixptje4FSFWEFqdW             |
|        84 | mum           | jghixpeqdW                     |
|        85 | nanaa         | 432432ixpeqdW                  |
|        86 | nnnniinn      | irewxpeqdW                     |
|        87 | iourewoiure   | rewixpeqdW                     |
|        88 | lkjfdsoiu     | dsaixpeqdW                     |
|        89 | vcxnoj        | dasdasixpeqdW                  |
|        90 | ioyuwer       | ixpeqdvcxvcxW                  |
|        91 | kaka          | ixpeqdW                        |
|        92 | nini          | ixpeqdvcxW                     |
|        93 | zong          | ixpeqdWfdsfsdf                 |
|        94 | nana          | ixpefdsafdsqdW                 |
|        95 | ninna         | ixpeqOPUIFDSFDSdW              |
+-----------+---------------+--------------------------------+
95 rows in set (0.002 sec)

```
### Summary

