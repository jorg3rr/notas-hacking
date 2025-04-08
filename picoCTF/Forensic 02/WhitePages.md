### Descripción

Dejé de usar YellowPages y pasé a WhitePages... ¡Pero [la página que me dieron](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) está toda en blanco!

### Solución
1. Puse este comando en la terminal de linux  xxd -l 100 whitepages.txt Este comando usa `xxd` para mostrar los primeros **100 bytes** del archivo `whitepages.txt` en formato **hexadecimal y ASCII**. Es útil para inspeccionar el contenido binario de un archivo.
2. Después agregue el siguiente comando: sed 's/\xe2\x80\x83/0/g' whitepages.txt | sed 's/\x20/1/g'  Este comando usa `sed` para **reemplazar ciertos caracteres en el archivo**:
	**`sed 's/\xe2\x80\x83/0/g' whitepages.txt'`**
    
    - Busca el **carácter Unicode `U+2003` (EM SPACE, un espacio largo)**
        
    - Lo reemplaza por **"0"**
        
    - `g` significa **"global"**, es decir, reemplaza todas las ocurrencias en cada línea.
        
	 **`| sed 's/\x20/1/g'`**
    
    - El `|` **toma la salida del primer `sed` y la pasa al segundo `sed`**.
        
    - `\x20` es el código hexadecimal para un **espacio normal** (`" "`).
        
    - Lo reemplaza con **"1"**.
3. Finalmente el resultado lo pegue en CyberChef para hacer la conversión FromBinary
   
### Resultado:
   picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}