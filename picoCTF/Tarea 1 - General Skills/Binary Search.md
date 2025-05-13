##### Descripción

¿Quieres jugar un juego? A medida que use más shells, ¡es posible que le interese saber cómo funcionan! La búsqueda binaria es un algoritmo clásico que se utiliza para encontrar rápidamente un elemento en una lista ordenada. ¿Puedes encontrar la bandera? Tendrás 1000 posibilidades y solo 10 conjeturas.

La ciberseguridad suele implicar una gran cantidad de datos que revisar, desde registros, informes de vulnerabilidades y análisis forenses. ¡Practicar los fundamentos manualmente podría ayudarte en el futuro cuando tengas que escribir tus propias herramientas!

##### Archivos proporcionados:

- `challenge.zip`: Archivo comprimido que contiene los datos del reto.
    

##### Solución

El objetivo es utilizar la búsqueda binaria para encontrar el número correcto en el menor número de intentos posible.

##### Pasos:

1. **Conectarse al servidor SSH**
    
    ```
    ssh -p 64902 ctf-player@atlas.picoctf.net
    ```
    
    Se ingresa la contraseña proporcionada (oculta en el terminal).
    
2. **Seguir las instrucciones del juego**
    
    El servidor piensa en un número entre 1 y 1000, y el usuario debe adivinarlo utilizando el método de búsqueda binaria:
    
    - Se comienza con un número intermedio:
        
        ```
        Enter your guess: 400
        Lower! Try again.
        ```
        
    - Se ajusta el rango según la respuesta del servidor:
        
        ```
        Enter your guess: 300
        Higher! Try again.
        Enter your guess: 350
        Higher! Try again.
        ```
        
    - Se sigue reduciendo el intervalo hasta encontrar el número correcto:
        
        ```
        Enter your guess: 383
        Congratulations! You guessed the correct number: 383
        ```
        
3. **Obtener la bandera**
    
    Una vez que se adivina correctamente el número, el servidor devuelve la bandera:
    
    ```
    Here's your flag: picoCTF{g00d_gu355_bee04a2a}
    ```
    

##### Resultado

La bandera encontrada es:

```
picoCTF{g00d_gu355_bee04a2a}
```

##### Notas adicionales

- La búsqueda binaria es una técnica eficiente para encontrar valores en un conjunto ordenado.
    
- Siempre dividir el rango por la mitad para optimizar las conjeturas.
    
- Aplicar esta estrategia a otros problemas con rangos numéricos puede acelerar la resolución.
    

##### Referencias

- [Conceptos de búsqueda binaria](https://en.wikipedia.org/wiki/Binary_search_algorithm)