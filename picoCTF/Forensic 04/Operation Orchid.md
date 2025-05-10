### Descripción

Descargue esta imagen de disco y busque la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen de disco no en su directorio de inicio.`/tmp`

- [Descargar imagen de disco comprimido](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)

### Solución

1. Podemos descomprimir la imagen de disco con y luego montarla con .`gunzip disk.flag.img.gz``sudo kpartx -av disk.flag.img`
    
2. En el volumen montado, hay un archivo y . Mirando vemos lo siguiente:`/root/flag.txt.enc``.ash_history``.ash_history`
    


```
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
```

1. Por lo tanto, parece que fue encriptado y salado usando aes256 con la clave .`flag.txt.enc``unbreakablepassword1234567`
    
2. Podemos descifrar el e imprimir la bandera con (observe la opción adicional).`flag.txt.enc``openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567; cat flag.txt``-d`
    

### Bandera

`picoCTF{h4un71ng_p457_0a710765}`