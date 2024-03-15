# Block Cipher & DES: A Sneak Peek into Secure Encryption 🛡️

## Block Cipher:
- A block cipher is a symmetric key encryption algorithm operating on fixed-length data blocks. 
- It encrypts or decrypts a plaintext block into a ciphertext block using the same key. 
- The input and output blocks are of fixed size, typically 64 or 128 bits.
- Block ciphers are commonly used to provide confidentiality for data transmission and storage. 
## Data Encryption Standard (DES):
- DES is a symmetric key block cipher algorithm. 
- It was designed to provide secure encryption for unclassified government communications.
### Key features of DES include:
- **Block Size:** 64 bits
- **Key Size:** 56 bits (with 8 parity bits)
- **Number of Rounds:** 16
- **Subkey Generation:** DES uses key expansion to generate 16 subkeys, one for each round of encryption.
- **Feistel Structure:** DES employs a Feistel cipher structure, where each round consists of multiple operations, including permutation, substitution, and XOR.

![[des.png]]