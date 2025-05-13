#### Descripción

ROJO, ROJO, ROJO, ROJODescargar la imagen: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

### Solución
Al abrir el archivo de imagen en sí, solo podemos ver lo siguiente. Sin embargo, saber que **la esteganografía generalmente se combina con la medicina forense en una sola categoría.** Me encargué de intentar investigar la imagen más a fondo utilizando herramientas esteganográficas.

![](https://miro.medium.com/v2/resize:fit:160/1*Erjeo7oIcLwb0MPr2WhsiQ.png)

Descubrí que zsteg era una buena opción para empezar, ya que **zsteg** es una herramienta utilizada para **la detección de esteganografía** en **imágenes PNG y BMP**. Y dado que estamos tratando con un archivo .PNG, pensé que sería prudente comenzar con esto.

zsteg **analiza esencialmente las imágenes** para detectar **datos ocultos** (esteganografía). Y es capaz de extraer información oculta de **LSB (Bit Menos Significativo)** y otras **técnicas esteganográficas**.

![](https://miro.medium.com/v2/resize:fit:875/1*W8Gslz0C587HEmpGWYJK1Q.png)

Usando el webshell pico y el comando:

> zsteg -a red.png

Pude encontrar lo que parecía una cadena codificada en base64:

> "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="

¡Lo llevé a [CyberChef](https://gchq.github.io/CyberChef) para descifrarlo y encontré la bandera!

### Bandera
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}