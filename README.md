This Rust program shows how to utilize the TFHE (Fast Fully Homomorphic Encryption over Torus) library to encrypt huge integers, produce pseudo-random numbers, and serialize the encrypted data for storage or transmission.  This is especially useful in situations when encrypted values must be securely processed without first being decrypted.
## Features
- **Fully Homomorphic Encryption (FHE):** Encrypts data in such a way that it can be processed without needing to decrypt it, maintaining data privacy.
- **Large Integer Encryption:** Supports encryption of large integers (e.g., u32).
- **Pseudo-Random Number Generation:** Generates a pseudo-random number based on encrypted data.
- **Data Serialization:** Safely serializes the encrypted data into a buffer for storage or transmission.



## Requirements
- **Rust:** Ensure you have the latest stable version of Rust installed.
- **Rust version:** a minimum Rust version of $1.73$ is required to compile TFHE-rs.
- **TFHE Library:** The project depends on the TFHE library for fully homomorphic encryption. Ensure the library is included in your `Cargo.toml` file. 

``` 
#To include library run:
cargo add tfhe

#Alternatively paste the line below in 'Cargo.toml' 
#For x86_64 machine running a Unix-like OS:

tfhe = { version = "0.7.2", features = [ "boolean", "shortint", "integer", "x86_64-unix" ] }
#For ARM machine running a Unix-like OS:

tfhe = { version = "0.7.2", features = [ "boolean", "shortint", "integer", "aarch64-unix" ] }
#For x86_64 machines with the rdseed instruction running Windows:

tfhe = { version = "*", features = ["boolean", "shortint", "integer", "x86_64"] }

#ensure to build cargo after adding the tfhe library
cargo run build
```
## Usage 
- **Configure Encryption Parameters:** The program sets up encryption parameters optimized for large integers using ConfigBuilder.
- **Generate Client and Server Keys:** Generates the keys needed for encryption and decryption.
- **Set Server Key:** The server key is set to enable decryption on the server side.
- **Encrypt a Large Integer:** Encrypts a large integer (u32) using the client's key.
- **Generate Pseudo-Random Number (Optional):** Generates a pseudo-random number with a specified number of bits.
- **Serialize Encrypted Data:** Safely serializes the ciphertext into a buffer, which can be used for storage or transmission.
- **Complete the Process:** Prints the serialized ciphertext and indicates completion.
## Customization
- **Input Message:** Modify the input_message variable to encrypt different integers.
- **Random Bits Count:** Change random_bits_count to generate a different number of pseudo-random bits.
- **Buffer Size:** Adjust the buffer size in the safe_serialize function to accommodate larger or smaller serialized data.
- If serialization fails, consider increasing the buffer size.
## Run code
>[!TIP]
> Performance: for optimal performance, it is highly recommended to run code that uses TFHE-rs in release mode with cargo's --release flag.
>```
>cargo -- run release
>```
 ## Contributing
  - If you intend to contribute to this project, fork the repository and make a pull request.

  ## Installation

- To use this project, you need to have Rust installed on your machine.
- If Rust is not installed, follow the instructions on the [official Rust website](https://www.rust-lang.org/tools/install) to install it.
- After installing Rust, clone this repository or copy the code into a Rust project, Compile and run the code using cargo run.

```bash
git clone https://github.com/cypriansakwa/Fully_Homomorphic_Encryption_and_Serialization_of_Large_Integers_with_TFHE.git
cd Fully_Homomorphic_Encryption_and_Serialization_of_Large_Integers_with_TFHE
