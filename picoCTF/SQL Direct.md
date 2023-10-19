#web_exploitation #sql #postgreSQL
#### Description
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 59093 -U postgres pico`Password is `postgres`

### Solution

después de conectarnos a la base de datos buscando en las tablas damos con la bandera 

```sql
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 59093 -U postgres pico
Password for user postgres: 
psql (16.0 (Debian 16.0-2), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.


pico-# \l                                                     
						List of databases
   Name    |  Owner   | Encoding | Locale Provider |  Collate   |   Ctype    | ICU Locale | ICU Rules |   Access privileges   
-----------+----------+----------+-----------------+------------+------------+------------+-----------+-----------------------
 pico      | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | 
 postgres  | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | 
 template0 | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/postgres          +
           |          |          |                 |            |            |            |           | postgres=CTc/postgres
 template1 | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/postgres          +
           |          |          |                 |            |            |            |           | postgres=CTc/postgres
(4 rows)



pico-# \c pico
psql (16.0 (Debian 16.0-2), server 15.2 (Debian 15.2-1.pgdg110+1))
You are now connected to database "pico" as user "postgres".
pico-# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# SELECT * FROM  public.flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```


### Flag
picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}