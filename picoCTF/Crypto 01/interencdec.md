#### Descripción

¿Puedes obtener el significado real de este archivo?Descarga el archivo [aquí](https://artifacts.picoctf.net/c_titan/108/enc_flag).

## Solución

Si abrimos el archivo, obtenemos la siguiente cadena:

`YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyMHdNakV5TnpVNGZRPT0nCg==`

Esto parece una cadena base64, así que intentemos decodificarla. El resultado sería el siguiente:

`b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX20wMjEyNzU4fQ=='`

Sin embargo, el resultado sigue pareciendo una cadena codificada en **base64**. Parece que los datos podrían haber sido codificados varias veces. Así que tenemos que decodificarlo de nuevo.

Tenga en cuenta que eliminé **b' '** de la cadena y decodifiqué el texto en el medio.

**Resultado**: `wpjvJAM{jhlzhy_k3jy9wa3k_m0212758}`

### Bandera
picoCTF{caesar_d3cr9pt3d_a47c6d69}