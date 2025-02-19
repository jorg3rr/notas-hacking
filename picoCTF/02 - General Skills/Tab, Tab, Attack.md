#### Descripción

El uso de **tab-complete** en la Terminal agregará años a tu vida, especialmente cuando se trata de estructuras de directorios y nombres de archivos largos y complicados.

Archivo proporcionado: **Addadshashanammu.zip**

#### Solución

El objetivo es explorar el archivo ZIP y encontrar la bandera.
##### Métodos:

1. **Listar el contenido del archivo ZIP:**
    `unzip -l Addadshashanammu.zip`
    Esto mostrará los archivos dentro del ZIP.
    
2. **Extraer el archivo ZIP:**
    `unzip Addadshashanammu.zip`
    
3. **Navegar por los archivos extraídos con Tab-Complete:**
    `cd Addad<TAB>`
    
4. **Buscar la bandera dentro de los archivos extraídos:**
    `grep -r "picoCTF" .`
    
5. **Usar `strings` en archivos binarios:**  
    Si hay archivos no legibles, usar:
    `strings archivo | grep picoCTF`
    
##### Resultado esperado
`picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}`

Notas adicionales
- Explorar subdirectorios con `ls -R`.
- Si hay archivos `.tar.gz`, `.txt` u otros dentro del ZIP, descomprimirlos y revisarlos.

#### Referencias

- Comando unzip - Linux
- Comando grep - Linux