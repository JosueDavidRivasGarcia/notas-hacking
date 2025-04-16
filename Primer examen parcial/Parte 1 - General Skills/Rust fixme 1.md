## Reto:  Rust fixme 1
### Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
### Solución
1. Descargamos la carpeta comprimida
```shell
wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
```

2. Extraemos los archivos de la carpeta
```shell
tar -xvzf fixme1.tar.gz
```

3. Entramos a la carpeta
```shell
cd fixme1
```

4. Compilamos el archivo main.rs. Lanza errores así que entramos al editor de texto para buscarlos y corregirlos

```
cd src
nano main.rs
```

```rust
use xor_cryptor::XORCryptor;
 
fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", >

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
```

```rust
/// Corregimos

use xor_cryptor::XORCryptor;
 
fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", >

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        "{}:?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}
```

5. Compilamos y ejecutamos el código

```
cargo build
output: 
Compiling rust_proj v0.1.0 (/home/sailork/fixme1)
Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.69s

cargo run
ouput: 
Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.02s
Running `/home/sailork/fixme1/target/debug/rust_proj`
```

6. Obtenemos la bandera

```
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```


### Notas adicionales
### Referencias

 
