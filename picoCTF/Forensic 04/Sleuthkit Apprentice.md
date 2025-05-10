#### Descripción

Descargue esta imagen de disco y busque la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`

- [Descargar imagen de disco comprimido](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)

### Solución
`fls` command[](https://tan-junwei.github.io/CTF-Writeups/PicoCTF/Forensics/Sleuthkit-Apprentice#fls-command)

![](https://tan-junwei.github.io/CTF-Writeups/Assets/PicoCTF-Sleuthkit-Apprentice-4.png) El comando enumera los nombres de archivos y directorios de una imagen de disco. También utilicé la bandera para buscar recursivamente archivos y directorios en cada partición.`fls``-r`

No había mucho que pareciera de interés en la primera partición. Sin embargo, cuando ejecuté el mismo comando en la tercera partición, reveló una gran cantidad de archivos y directorios presentes en esta partición.

![](https://tan-junwei.github.io/CTF-Writeups/Assets/PicoCTF-Sleuthkit-Apprentice-5.png)

Luego corrí y encontré 2 archivos en esta partición. Posteriormente, probé en ambos archivos y obtuve la bandera.`fls -o 360448 -r disk.flag.img | grep flag``.txt``icat`

> El uso de `icat`
> 
> `icat` se utiliza para generar el contenido de un archivo en función de su número de inodo Especificar el desplazamiento de la partición y el número de inodo como tal permite mostrar el contenido del archivo.`icat -o <img-offset> <image-name> <inode-number>`

icat -o 360448 disk.flag.img 2371

> Bandera
> 
> picoCTF{by73_5urf3r_adac6cb4}