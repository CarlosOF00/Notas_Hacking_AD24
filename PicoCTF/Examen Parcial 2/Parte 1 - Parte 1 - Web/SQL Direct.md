## Descripción 
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2/tmp]
└─$ psql -h saturn.picoctf.net -p 64960 -U postgres pico

Password for user postgres: 
psql (16.3 (Debian 16.3-1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```

## Notas Adicionales
En **PostgreSQL**, puedes usar el comando `\dt` en el cliente de línea de comandos `psql` para listar todas las tablas.

## Referencias 
https://play.picoctf.org/practice/challenge/303
[Cómo listar todas las tablas de una base de datos en PostgreSQL (thedevelopmentstages.com)](https://thedevelopmentstages.com/listar-todas-las-tablas-de-una-base-de-datos-en-postgresql/)