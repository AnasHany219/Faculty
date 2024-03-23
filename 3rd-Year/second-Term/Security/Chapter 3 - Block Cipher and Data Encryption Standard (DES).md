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

### 🔐 DES Key Generation

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
### Data Encryption
#### **Initial Permutation (IP):**

- **Purpose:** IP orchestrates a stunning transformation, reshuffling the 64-bit plaintext block into a new configuration dictated by a predefined pattern.
- **Process:**
  - The 64-bit input block unfolds into an elegant tableau of 8 rows and 8 columns.
  - Each bit of the output finds its place by selecting the corresponding bit from the input block, guided by a fixed mapping.
  - For instance:
    ```
    58 50 42 34 26 18 10 2
    60 52 44 36 28 20 12 4
    62 54 46 38 30 22 14 6
    64 56 48 40 32 24 16 8
    57 49 41 33 25 17 9  1
    59 51 43 35 27 19 11 3
    61 53 45 37 29 21 13 5
    63 55 47 39 31 23 15 7
    ```
  - The first bit of the output derives from the $58^{th}$ bit of the input, followed by the $50^{th}$ bit, and so forth, culminating in the $7^{th}$ bit of the input.
#### **DES Round:**
- ![[DES Round.png]]
- **Initial Permutation (IP):** 🔄
  - The 64-bit input takes center stage, gracefully dividing into two equal halves: a 32-bit left half $L_{i-1}$ and a 32-bit right half $R_{i-1}$.
- **Expansion & Permutation:** 🌌
  - $R_{i-1}$ embarks on a daring expansion, venturing into uncharted territory of 48-bits, while Permutation orchestrates a mesmerizing rearrangement, painting the canvas with intricate patterns.
- **Mangler Function F & XOR:** ⚙️
  - A 48-bit subkey emerges, joining $R_{i-1}$ on a thrilling journey through the Mangler Function. Their energies collide in a fierce $\large \oplus$ duel, forging a breathtaking new creation.
  - **Expansion/Permutation (E-table):**
    - The 32-bit input expands to 48-bits by selecting specific bits according to a predefined table.
  - **XOR $\large \oplus$:**
    - The expanded output is XORed with a corresponding subkey, introducing randomness.
  - **Substitution/Choice (S-Box):**
    - After mixing in the subkeys, the block is divided into eight block each block contain 6-bit.
    - The input to each S-Box is 6 bits and the output is 4-bits.
  - **Permutation (P):**
    - The 32-bit outputs of the S-boxes are rearranged using the permutation box P-box.
- **XOR with Left Half:** 🌀
  - The transformed bits from the Mangler Function reunite with $L_{i-1}$ in a harmonious dance of XOR. Together, they sculpt the destiny of the next round, their union echoing across the realms of encryption.
- **Conclusion:** 🎇
$$\large L_i = R_{i-1}, \quad\quad  R_i = L_{i-1} ⊕ P(S(K_i + E(R_{i-1})))$$
#### 32-bit Switch (SW):
- At the end of the sixteenth round with 16 sub keys we have the blocks $L_16$ and $R_16$ each block 32 bit.
- We then reverse the order of the two blocks into the 64-bit block
#### Inversion of Initial Permutation ($IP^{-1}$)
- Perform the following permutation on the block $R_16 \ L_16$ Final Permutation ($IP^{-1}$)
---
### Example - 01: 
- Let M be the plain-text message $M = (0123 \ 4567 \ 89AB \ CDEF)_{16}$, where M is in hexadecimal `base 16` format. and the `key = 1334 5779 9BBC DFF1` 

#### 🔐 Create 16 subkeys

- All steps is here (16-Keys)[[#🔐 DES Key Generation]]
#### 🔐 Encode each 64-bit block of data.
##### Initial Permutation (IP):

1. 🔢 **Binary Conversion**: 
   ```
   0000 0001 0010 0011 0100 0101 0110 0111 1000 1001 1010 1011 1100 1101 1110 1111
   ```

2. Apply the Permutations 🔀:
   ```
   Initial Permutation (IP): 
   58 50 42 34 26 18 10 2 
   60 52 44 36 28 20 12 4 
   62 54 46 38 30 22 14 6 
   64 56 48 40 32 24 16 8 
   57 49 41 33 25 17 9  1 
   59 51 43 35 27 19 11 3 
   61 53 45 37 29 21 13 5 
   63 55 47 39 31 23 15 7

	M = 0000 0001 0010 0011 0100 0101 0110 0111 
		1000 1001 1010 1011 1100 1101 1110 1111

	IP = 1100 1100 0000 0000 1100 1100 1111 1111 
		 1111 0000 1010 1010 1111 0000 1010 1010
	```

3. Divide the permuted block **IP** into a left half $L_0$ of 32 bits, and a right half $R_0$ of 32 bits.
	```
	L0 = 1100 1100 0000 0000 1100 1100 1111 1111  
	R0 = 1111 0000 1010 1010 1111 0000 1010 1010 --> L1
	```
##### DES Round - 01:

1. Expansion E table $E(R_{n-1})$
	```
    E(R0):
	32   1   2   3   4   5  -->  0  1  1  1  1  0  
	 4   5   6   7   8   9  -->  1  0  0  0  0  1
	 8   9  10  11  12  13  -->  0  1  0  1  0  1
	12  13  14  15  16  17  -->  0  1  0  1  0  1
	16  17  18  19  20  21  -->  0  1  1  1  1  0
	20  21  22  23  24  25  -->  1  0  0  0  0  1
	24  25  26  27  28  29  -->  0  1  0  1  0  1
	28  29  30  31  32   1  -->  0  1  0  1  0  1

	E(R0) = 011110 100001 010101 010101 011110 100001 010101 010101
	```

2. Key Mixing $Key_{01} + E(R_{n-1})$
	```
	E(R0) ⊕ Key01:
	011110 100001 010101 010101 011110 100001 010101 010101  ⊕ 
	000110 110000 001011 101111 111111 000111 000001 110010
	----------------------------------------------------------
	011000 010001 011110 111010 100001 100110 010100 100111
	```

3.  S-Box 
	```
	-------------------------- S1 --------------------------
     14  4  13  1   2 15  11  8   3 10   6 12   5  9   0  7
      0 15   7  4  14  2  13  1  10  6  12 11   9  5   3  8
      4  1  14  8  13  6   2 11  15 12   9  7   3 10   5  0
     15 12   8  2   4  9   1  7   5 11   3 14  10  0   6 13
	-------------------------- S2 --------------------------
     15  1   8 14   6 11   3  4   9  7   2 13  12  0   5 10
      3 13   4  7  15  2   8 14  12  0   1 10   6  9  11  5
      0 14   7 11  10  4  13  1   5  8  12  6   9  3   2 15
     13  8  10  1   3 15   4  2  11  6   7 12   0  5  14  9
	-------------------------- S3 --------------------------
     10  0   9 14   6  3  15  5   1 13  12  7  11  4   2  8
     13  7   0  9   3  4   6 10   2  8   5 14  12 11  15  1
     13  6   4  9   8 15   3  0  11  1   2 12   5 10  14  7
      1 10  13  0   6  9   8  7   4 15  14  3  11  5   2 12
	-------------------------- S4 --------------------------
      7 13  14  3   0  6   9 10   1  2   8  5  11 12   4 15
     13  8  11  5   6 15   0  3   4  7   2 12   1 10  14  9
     10  6   9  0  12 11   7 13  15  1   3 14   5  2   8  4
      3 15   0  6  10  1  13  8   9  4   5 11  12  7   2 14
	-------------------------- S5 --------------------------
      2 12   4  1   7 10  11  6   8  5   3 15  13  0  14  9
     14 11   2 12   4  7  13  1   5  0  15 10   3  9   8  6
      4  2   1 11  10 13   7  8  15  9  12  5   6  3   0 14
     11  8  12  7   1 14   2 13   6 15   0  9  10  4   5  3
	-------------------------- S6 --------------------------
     12  1  10 15   9  2   6  8   0 13   3  4  14  7   5 11
     10 15   4  2   7 12   9  5   6  1  13 14   0 11   3  8
      9 14  15  5   2  8  12  3   7  0   4 10   1 13  11  6
      4  3   2 12   9  5  15 10  11 14   1  7   6  0   8 13
	-------------------------- S7 --------------------------
      4 11   2 14  15  0   8 13   3 12   9  7   5 10   6  1
     13  0  11  7   4  9   1 10  14  3   5 12   2 15   8  6
      1  4  11 13  12  3   7 14  10 15   6  8   0  5   9  2
      6 11  13  8   1  4  10  7   9  5   0 15  14  2   3 12
	-------------------------- S8 --------------------------
     13  2   8  4   6 15  11  1  10  9   3 14   5  0  12  7
      1 15  13  8  10  3   7  4  12  5   6 11   0 14   9  2
      7 11   4  1   9 12  14  2   0  6  10 13  15  3   5  8
      2  1  14  7   4 10   8 13  15 12   9  0   3  5   6 11
	```

4. Apply S-box substitution for each block  $S(Key_{01} + E(R_{n-1}))$:
	```
	B1 = 011000 -> S1B1 = 0101
	B2 = 010001 -> S2B2 = 1100
	B3 = 011110 -> S3B3 = 0010
	B4 = 111010 -> S4B4 = 1111
	B5 = 100001 -> S5B5 = 0000
	B6 = 100110 -> S6B6 = 1100
	B7 = 010100 -> S7B7 = 1111
	B8 = 100111 -> S8B8 = 1100
	---------------------------------------
	S(K+E) = S1B1 S2B2 S3B3 S4B4 S5B5 S6B6 S7B7 S8B8
	S(K+E) = 0101 1100 0010 1111 0000 1100 1111 1100
	```

5. Apply The permutation $f = P(S(Key_{01} + E(R_{n-1})))$ 
	```
	P(s):
	16   7  20  21    -->    0  0  1  0
    29  12  28  17    -->    0  0  1  1
     1  15  23  26    -->    0  1  0  0
     5  18  31  10    -->    1  0  1  0
     2   8  24  14    -->    1  0  1  0
    32  27   3   9    -->    1  0  0  1
    19  13  30   6    -->    1  0  1  1
	22  11   4  25    -->    1  0  1  1

	f = 0010 0011 0100 1010 1010 1001 1011 1011
	```

6. Apply $R_1 = L_0 + f(R_0, K1)$ By Xor ⊕
	```
	L0:  1100 1100 0000 0000 1100 1100 1111 1111  ⊕
	F1:   0010 0011 0100 1010 1010 1001 1011 1011
	----------------------------------------------
	R1:   1110 1111 0100 1010 0110 0101 0100 0100
	```
##### DES Round - [02 : 16]:

1. **Expansion E table $E(R_{n-1})$**:
   - Expand the right half $R_0$ using the expansion E table to obtain $E(R_0)$.

2. **Key Mixing $Key_{01} + E(R_{n-1})$**:
   - XOR the expanded right half $E(R_0)$ with the round subkey $Key_{01}$ to obtain $Key_{01} + E(R_0)$.

3. **S-Box**:
   - Apply S-box substitution to each block of $Key_{01} + E(R_0)$ to obtain the output of the S-boxes.

4. **Permutation $P$**:
   - Perform the permutation $P$ on the output of the S-boxes to obtain $f$.

5. **Apply $R_1 = L_0 + f(R_0, K1)$ By XOR ⊕**:
   - XOR the left half $L_0$ with $f(R_0, K1)$ to obtain the new right half $R_1$.
##### 32-bit Switch (SW):
- Swap $L_{16}R_{16}$ to $R_{16}L_{16}$
	```
	L16 = 0100 0011 0100 0010 0011 0010 0011 0100  
	R16 = 0000 1010 0100 1100 1101 1001 1001 0101
	---------------------------------------------
	R16L16 = 00001010 01001100 11011001 10010101 01000011 01000010 00110010 00110100
	```
##### Inversion of Initial Permutation ($IP^{-1}$)
```
	IP^{-1}:
		40     8   48    16    56   24    64   32
		39     7   47    15    55   23    63   31
		38     6   46    14    54   22    62   30
		37     5   45    13    53   21    61   29
		36     4   44    12    52   20    60   28
		35     3   43    11    51   19    59   27
		34     2   42    10    50   18    58   26
		33     1   41     9    49   17    57   25
		-----------------------------------------
	IP^{-1}: 
		10000101 11101000 00010011 01010100 00001111 00001010 10110100 00000101
	
	This is the encrypted form of 
	M = 0123456789ABCDEF: namely, 
	C = 85E813540F0AB405.
```


