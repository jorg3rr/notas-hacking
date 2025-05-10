#### Descripción

Descargue esta imagen de disco, busque la clave e inicie sesión en la máquina remota.Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`

- [Descargar imagen de disco](https://artifacts.picoctf.net/c/70/disk.img.gz)
- Máquina remota: `ssh -i key_file -p 50715 ctf-player@saturn.picoctf.net`

### Descripción
### Creación del archivo de salida[](https://tan-junwei.github.io/CTF-Writeups/PicoCTF/Forensics/Operation-Oni#making-the-output-file)

![](https://tan-junwei.github.io/CTF-Writeups/Assets/PicoCTF-operation-oni-5.5.png)

Después de ejecutar, parecía que contenía la clave privada ssh completa, por lo que escribiremos la salida de esto en un archivo para conectarlo al servidor SSH más adelante.`icat -o 206848 disk.img 2345``key.txt`

### Error de archivo de clave privada no protegida[](https://tan-junwei.github.io/CTF-Writeups/PicoCTF/Forensics/Operation-Oni#unprotected-private-key-file-error)

![](https://tan-junwei.github.io/CTF-Writeups/Assets/PicoCTF-operation-oni-6.png)


![](https://tan-junwei.github.io/CTF-Writeups/Assets/PicoCTF-operation-oni-7.png) Después de cambiar los permisos del archivo, podemos conectarnos con éxito al servidor SSH. Podemos correr y coger nuestra bandera.`ls``cat flag.txt`
### Bandera
picoCTF{k3y_5l3u7h_b5066e83}