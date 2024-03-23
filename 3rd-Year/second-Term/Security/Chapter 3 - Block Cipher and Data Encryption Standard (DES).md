# Block Cipher & DES: A Sneak Peek into Secure Encryption 🛡️

## Block Cipher:

- A `symmetric key` encryption algorithm operating on fixed-length data blocks. 
- It `encrypts` or `decrypts` a plaintext block into a ciphertext block using `the same key`. 
- The `input` and `output` blocks are of fixed size, typically `64 or 128 bits`.
- Block ciphers are commonly used to `provide confidentiality` for data transmission and storage. 
## Data Encryption Standard (DES):

- A `symmetric key` block cipher algorithm. 
- It was designed to `provide secure encryption` for unclassified government communications.
### Key features of DES include:

- **Block Size:** 64 bits.
- **Key Size:** 56 bits (with 8 parity bits).
- **Number of Rounds:** 16
- **Subkey Generation:** DES uses key expansion to generate `16 subkeys`, one for each round of encryption.
- **Feistel Structure:** DES employs a `Feistel cipher structure`, where each round consists of multiple operations, including `permutation`, `substitution`, and `XOR`.
- ![[DES.png]]

### 🔐 **DES Key Generation**

1. 🔢 **Binary Conversion**: Convert the hexadecimal key `1334 5779 9BBC DFF1` to binary:
   ```
   00010011 00110100 01010111 01111001 10011011 10111100 11011111 11110001
   ```

2. 🔀 **Odd Parity**: `Ensure` each block has an `odd number` of ones by `adding 1 if necessary`:
   ```
   00010011 00110101 01010111 01111001 10011011 10111101 11011111 11110001
   ```

3. ✂️ **Remove Last Bit**: Remove the `last` bit from each block:
   ```
   0001001  0011010  0101011  0111100  1001101  1011110  1101111  1111000
          08       16       24       32       40       48       56       64
   ```

4. 🔄 **Apply PC-1 Permutation**:
   ```
   PC-1:                                  Key-p:    
   57 49 41 33 25 17 9          -->       1  1  1  1  0  0  0
   1  58 50 42 34 26 18         -->       0  1  1  0  0  1  1
   10 2  59 51 43 35 27         -->       0  0  1  0  1  0  1
   19 11 3  60 52 44 36         -->       0  1  0  1  1  1  1
   63 55 47 39 31 23 15         -->       0  1  0  1  0  1  0  
   7  62 54 46 38 30 22         -->       1  0  1  1  0  0  1
   14 6  61 53 45 37 29         -->       1  0  0  1  1  1  1
   21 13 5  28 20 12 4          -->       0  0  0  1  1  1  1
   ```

5. 🔪 **Split into C0 and D0**:
   ```
   C0: 1111000 0110011 0010101 0101111    D0: 0101010 1011001 1001111 0001111
   ```

6. ⏪ **Apply Key Schedule - Shifts:** 1 for `1, 2, 9, 16` and 2 for the `others`:
   ```
   C01: 1110000 1100110 0101010 1011111   D01: 1010101 0110011 0011110 0011110
   C02: 1100001 1001100 1010101 0111111   D02: 0101010 1100110 0111100 0111101
   C03: 0000110 0110010 1010101 1111111   D03: 0101011 0011001 1110001 1110101
   C04: 0011001 1001010 1010111 1111100   D04: 0101100 1100111 1000111 1010101
   C05: 1100110 0101010 1011111 1110000   D05: 0110011 0011110 0011110 1010101
   C06: 0011001 0101010 1111111 1000011   D06: 1001100 1111000 1111010 1010101
   C07: 1100101 0101011 1111110 0001100   D07: 0110011 1100011 1101010 1010110
   C08: 0010101 0101111 1111000 0110011   D08: 1001111 0001111 0101010 1011001
   C09: 0101010 1011111 1110000 1100110   D09: 0011110 0011110 1010101 0110011
   C10: 0101010 1111111 1000011 0011001   D10: 1111000 1111010 1010101 1001100
   C11: 0101011 1111110 0001100 1100101   D11: 1100011 1101010 1010110 0110011
   C12: 0101111 1111000 0110011 0010101   D12: 0001111 0101010 1011001 1001111
   C13: 0111111 1100001 1001100 1010101   D13: 0111101 0101010 1100110 0111100
   C14: 1111111 0000110 0110010 1010101   D14: 1110101 0101011 0011001 1110001
   C15: 1111100 0011001 1001010 1010111   D15: 1010101 0101100 1100111 1000111
   C16: 1111000 0110011 0010101 0101111   D16: 0101010 1011001 1001111 0001111
	```

7. 🔄 **Apply PC-1 Permutation**:
   ```
   PC-2:
   14 17 11 24 1  5
   3  28 15 6  21 10
   23 19 12 4  26 8
   16 7  27 20 13 2
   41 52 31 37 47 55
   30 40 51 45 33 48
   44 49 39 56 34 53
   46 42 50 36 29 32
   
   Key01 = 000110 110000 001011 101111 111111 000111 000001 110010
   Key02 = 011110 011010 111011 011001 110110 111100 100111 100101
   Key03 = 010101 011111 110010 001010 010000 101100 111110 011001
   Key04 = 011100 101010 110111 010110 110110 110011 010100 011101
   Key05 = 011111 001110 110000 000111 111010 110101 001110 101000
   Key06 = 011000 111010 010100 111110 010100 000111 101100 101111
   Key07 = 111011 001000 010010 110111 111101 100001 100010 111100
   Key08 = 111101 111000 101000 111010 110000 010011 101111 111011
   Key09 = 111000 001101 101111 101011 111011 011110 011110 000001
   Key10 = 101100 011111 001101 000111 101110 100100 011001 001111
   Key11 = 001000 010101 111111 010011 110111 101101 001110 000110
   Key12 = 011101 010111 000111 110101 100101 000110 011111 101001
   Key13 = 100101 111100 010111 010001 111110 101011 101001 000001
   Key14 = 010111 110100 001110 110111 111100 101110 011100 111010
   Key15 = 101111 111001 000110 001101 001111 010011 111100 001010
   Key16 = 110010 110011 110110 001011 000011 100001 011111 110101
   ```
Each subkey is now ready for use in the DES algorithm! 🎉

---
### 


