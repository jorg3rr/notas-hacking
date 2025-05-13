#### Descripción

El Centro de Operaciones de Red (NOC) de su institución local recogió un sospechoso, están recibiendo información contradictoria sobre qué tipo de archivo Lo es. Te han traído como experto externo para examinar el expediente. Enlatar ¿Extraes toda la información de este extraño archivo?Descargue el archivo sospechoso [aquí](https://artifacts.picoctf.net/c_titan/8/flag2of2-final.pdf).

# Solución

Lo primero que hice cuando vi este PDF fue abrirlo en un editor hexadecimal. Puedes usar cualquier editor hexadecimal que quieras, pero yo usé [HexEd.it](https://hexed.it/).

HexEd.it vista de flag2of2-final.pdf

Inmediatamente, podemos ver que los primeros bytes dicen , este es el encabezado del archivo PNG. Esto nos dice que nuestro archivo PDF es en realidad un archivo PNG. Puedes leer más sobre los encabezados de archivos PNG [aquí](https://medium.com/@0xwan/png-structure-for-beginner-8363ce2a9f73).`PNG`

Entonces, cuando cambiamos el nombre de este flag2of2-final.png, obtenemos la primera mitad de la bandera: "picoCTF{f13u3n7_".

![](https://miro.medium.com/v2/resize:fit:63/1*gh8q2eHXGfZ8q-oKGUWfpA.png)

Primera mitad de la bandera

Combine esto con la segunda mitad en el pdf original: "1n_pn9_&_pdf_90974127}, obtenemos nuestra bandera completa: picoCTF{f13u3n7_1n_pn9_&_pdf_90974127}