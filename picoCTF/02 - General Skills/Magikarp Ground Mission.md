### **Descripción**

¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicie el contenedor, haga `ssh` y luego `ls` una vez conectado para comenzar.

Inicie sesión a través de **SSH** con las siguientes credenciales:

- **Usuario:** `ctf-player`
- **Contraseña:** `a13b7f9d`
- **Host:** `venus.picoctf.net`
- **Puerto:** `53080`

### **Solución**

1️⃣ Conectar al servidor usando `ssh`:

`ssh ctf-player@venus.picoctf.net -p 53080`

Cuando solicite la contraseña, introduce `a13b7f9d`.

2️⃣ Una vez dentro, listar los archivos y directorios disponibles:

`ls -la`

3️⃣ Navegar por los directorios sospechosos usando `cd`:

`cd nombre_del_directorio`

4️⃣ Leer archivos de texto para encontrar la bandera:

`cat nombre_del_archivo`

Usar `grep` para buscar **picoCTF** en todos los archivos:

`grep -r "picoCTF" .`

### **Revisar el contenido de los archivos**

1️⃣ **Ver el contenido de la primera bandera**

`cat 1of3.flag.txt`

2️⃣ **Leer las instrucciones para encontrar la segunda bandera**

`cat instructions-to-2of3.txt`

Ejecuta el siguiente comando para leer el archivo:

`cat /2of3.flag.txt`

Resultado esperado:
picoCTF{xxsh_0ut_0f_\/\/4t3r_71be5264}
### **Notas adicionales**
-  Puedes usar `pwd` para ver en qué directorio estás.
- Usa `tab` para autocompletar nombres de archivos y directorios.
### **Referencias**

- Manual de SSH
- [Comandos básicos de Linux](https://explainshell.com/)