#### Descripción

¿Has oído hablar de Rust? ¡Arregla los errores de sintaxis en este archivo de Rust para imprimir la bandera!Descarga el código de Rust [aquí](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).


## Solución

Primero vamos a pegar nuestro código:

use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS") // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        ret; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}

Entonces, de buenas a primeras, podemos ver que hay tres comentarios que resaltan los tres errores en el código. ¿Cómo terminamos las declaraciones en Rust? Con punto y coma (;). ¿Cómo volvemos en óxido? Usando 'return;'. ¿Cómo imprimimos una variable en la función println? En ese ejemplo específicamente podemos usar '{:?}`. Además, voy a eliminar todos los comentarios sin ninguna razón:

use xor_cryptor::XORCryptor;

fn main() {
    let key = String::from("CSUCKS");

    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let res = XORCryptor::new(&key);
    if res.is_err() {
        return;
    }
    let xrc = res.unwrap();

    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        "{:?}", 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}

Y cuando ejecutamos este código:

    Blocking waiting for file lock on package cache
    Blocking waiting for file lock on package cache
    Blocking waiting for file lock on package cache
    Blocking waiting for file lock on package cache
   Compiling rust_proj v0.1.0 (/home/runner/workspace)
    Building [=======================>   ] 11/12: rust_proj(bin)
    Finished dev profile [unoptimized + debuginfo] target(s) in 5.30s
     Running target/debug/rust_proj
"picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}"