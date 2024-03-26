## Goal
Connect to this PostgreSQL server and find the flag!
Additional details will be available after launching your challenge instance.
## Hints
What does a SQL database contain?
## Solution

```bash
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 50060 -U postgres pico
Password for user postgres: 
psql (16.2 (Debian 16.2-1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

````

## Notes

## References