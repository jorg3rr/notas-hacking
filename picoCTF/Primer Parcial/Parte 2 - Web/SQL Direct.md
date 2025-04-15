#### Descripción

¡Conéctese a este servidor PostgreSQL y encuentre la bandera!`psql -h saturn.picoctf.net -p 55515 -U postgres pico`La contraseña es `postgres`

## descripción

¡Conéctese a este servidor PostgreSQL y encuentre la bandera!

psql -h saturn.picoctf.net -p 49248 -U postgres pico

La contraseña es postgres

*Solución*

Bien, primero conectémonos al servidor de la base de datos:

|   |   |
|---|---|
|<br>1<br>|bash<br>psql -h saturn.picoctf.net -p 49248 -U postgres pico <br>|

La contraseña es 'postgres'

Vamos a enumerar primero todas las bases de datos

|   |   |
|---|---|
|<br> 1<br> 2<br> 3<br> 4<br> 5<br> 6<br> 7<br> 8<br> 9<br>10<br>11<br>|bash<br>pico=# \l<br>                                 List of databases<br>   Name    \|  Owner   \| Encoding \|  Collate   \|   Ctype    \|   Access privileges   <br>-----------+----------+----------+------------+------------+-----------------------<br> pico      \| postgres \| UTF8     \| en_US.utf8 \| en_US.utf8 \| <br> postgres  \| postgres \| UTF8     \| en_US.utf8 \| en_US.utf8 \| <br> template0 \| postgres \| UTF8     \| en_US.utf8 \| en_US.utf8 \| =c/postgres          +<br>           \|          \|          \|            \|            \| postgres=CTc/postgres<br> template1 \| postgres \| UTF8     \| en_US.utf8 \| en_US.utf8 \| =c/postgres          +<br>           \|          \|          \|            \|            \| postgres=CTc/postgres<br>(4 rows)<br>|

Conéctese a la base de datos 'pico'

|   |   |
|---|---|
|<br>1<br>|bash<br>pico=# \c pico<br>|

Enumerar todas las tablas

|   |   |
|---|---|
|<br>1<br>2<br>3<br>4<br>5<br>6<br>|bash<br>pico=# \dt<br>         List of relations<br> Schema \| Name  \| Type  \|  Owner   <br>--------+-------+-------+----------<br> public \| flags \| table \| postgres<br>(1 row)<br>|

la mesa 'banderas' suena interesante ...

Veamos el contenido:

|   |   |
|---|---|
|<br>1<br>2<br>3<br>4<br>5<br>6<br>7<br>|bash<br>pico=# select * from flags;<br> id \| firstname \| lastname  \|                address                 <br>----+-----------+-----------+----------------------------------------<br>  1 \| Luke      \| Skywalker \| picoCTF{L3arN_S0m3_5qL_t0d4Y_a26695df}<br>  2 \| Leia      \| Organa    \| Alderaan<br>  3 \| Han       \| Solo      \| Corellia<br>(3 rows)<br>|

Ahí está nuestra bandera.

|                 |                                                              |
| --------------- | ------------------------------------------------------------ |
| <br>1<br> | fallback<br>picoCTF{L3arN_S0m3_5qL_t0d4Y_a26695df}<br> |

*Respuesta en el formato del concurso:*
picoCTF{L3arN_S0m3_5qL_t0d4Y_a26695df}