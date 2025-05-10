### Descripción

Descargue la imagen de disco y utilícela para encontrar el tamaño del Linux partición. Conéctese al servicio de verificación remota para verificar su respuesta y obtener la bandera.`mmls`Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`[Descargar imagen de disco](https://artifacts.picoctf.net/c/164/disk.img.gz)Programa de verificación de acceso: `nc saturn.picoctf.net 50827`

### Solución
```shell
$ gzip -d disk.img.gz
$ mmls disk.img
```

### Bandera
`picoCTF{mm15_f7w!}`