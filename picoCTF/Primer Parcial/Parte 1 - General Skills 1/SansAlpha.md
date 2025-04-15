### Solución
1. Captura de la bandera codificada:*

- Asignamos el truco base64 para a una variable llamada . Esta variable contendría el comando real./???/????64_1/bin/base64
- A continuación, utilizamos la expansión del parámetro de shell () para extraer el primer elemento (el comando real) de las coincidencias potencialmente múltiples capturadas por el comodín."${_1[0]}"

2. Decodificando la bandera Base64:*

- Finalmente, con el indicador codificado en base64 recuperado usando (otra búsqueda comodín para archivos con cualquier extensión de tres caracteres)"${_1[0]} */????.???

- [Utilicé Base64 Decode and Encode — Online](https://www.base64decode.org/) para revelar la bandera del desafío.

*Respuesta en el formato del concurso:*
picoCTF{7h15_mu171v3r53_15_m4dn355_640b6add}