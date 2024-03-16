# 🛡️ Introduction to Classical Substitution Ciphers 🌐

## Symmetric Encryption:
- Symmetric encryption, also known as `conventional` or `private-key` encryption.
- Using a `single secret key` shared between the `sender` and `receiver` for both encryption and decryption.

## Basic Terminology:
- `Plain Text`: Original unencrypted message.
- `Cipher Text`: Encrypted message produced after applying an encryption algorithm.
- `Cipher`: Algorithm for encryption and decryption.
- `Key`: Information used by the encryption algorithm.
- `Encipher (Encrypt)`: Process of converting plaintext into ciphertext.
- `Decipher (Decrypt)`: Process of converting ciphertext back into plaintext.
- `Cryptography`: Science and practice of secure communication.
- `Cryptanalysis`: Study of analyzing information systems.
- `Cryptology`: Study of secure communication and related disciplines.

## Requirements for Encryption:
- A strong encryption algorithm and a secret key.
- `Encryption process (Encrypt)`: Converts plaintext (x) into ciphertext (y) using the encryption key (k), denoted as `E(k, x)`.
- `Decryption process (Decrypt)`: Converts ciphertext (y) back into plaintext (x) using the decryption key (k), denoted as `D(k, y)`.

## Cryptography:
### Operations:
- `Substitution`: Replaces plaintext with ciphertext based on a rule.
- `Transposition`: Rearranges plaintext characters.
- `Product`: Combines substitution and transposition.
### Number of Keys:
- `Single Key`: Shared between sender and receiver (private).
- `Two Keys`: Public key for encryption, private key for decryption.
### Processing Methods:
- `Block`: Encrypts fixed-size blocks of plaintext independently.
- `Stream`: Encrypts or decrypts data bit-by-bit or byte-by-byte in real-time.

## Cryptanalysis:
- `Cryptanalytic Attack`: Breaks encryption by analyzing ciphertext, exploiting algorithm or key weaknesses.
- `Brute Force Attack`: Tries all possible keys until the correct one is found.
## Classical Substitution Ciphers: 
### 01) Caesar Cipher
- `Key`: Same for both encryption and decryption (private).
- `Encrypt`: Combine plain text with a key (shift) to produce cipher text using the formula:
$$C(char) = (p + k) \ mod \ n$$
#### **Example:**
  - Plain Text: "HELLO"
  - Key (Shift): 3
	  - H $\rightarrow$ K (shifted 3 positions)
	  - E $\rightarrow$ H
	  - L $\rightarrow$ O
	  - L $\rightarrow$ O
	  - O $\rightarrow$ R
  - Encrypted Text: "KHOOR"
- Decrypt: Reverse the encryption process to recover plain text using the formula:
$$P(char) = (c - k) \ mod  \ n$$
#### Example:
 - K $\rightarrow$ H (shifted back 3 positions)
 - H $\rightarrow$ E
 - O $\rightarrow$ L
 - O $\rightarrow$ L
 - R $\rightarrow$ O
 - Decrypted Text: "HELLO"

<hr>

### 02) Merging Playfair Cipher:

#### **Playfair Cipher:**
- **Key:** Non-repeating, non-meaningful keyphrase or keyword.

**Key Generation:**
1. Choose a key phrase or keyword without repeating characters.
2. Construct a 5x5 matrix (Playfair grid) using the keyphrase. Fill the matrix row by row, excluding any duplicate letters and omitting "J" (usually "I" and "J" are combined into one cell).
3. Fill the remaining cells of the matrix with the remaining letters of the alphabet, omitting "J".

**Encryption Process:**
1. Remove any spaces and punctuation from the plaintext message.
2. Break the plaintext into pairs of characters (digraphs).
3. If a pair contains the same letter, insert an "X" between them.
4. For each pair of characters:
   - Locate the characters in the Playfair grid.
   - If both characters are in the same row, replace them with the characters to their right, wrapping around if necessary.
   - If both characters are in the same column, replace them with the characters below them, wrapping around if necessary.
   - If the characters form a rectangle, take the opposite corners of the rectangle as the ciphertext.
   - If the characters are in different rows and columns, form a rectangle with them and take the opposite corners.
5. Repeat this process for all character pairs in the plaintext.

#### **Example:**
- keyphrase $\large\rightarrow$ "MONARCHY"
- The plaintext message $\large\rightarrow$ "PLEASE TRANSFER ONE MILLION DOLLAR".
##### Step 1: Key Generation
Construct the Playfair grid using the keyphrase "MONARCHY":

```
M O N A R
C H Y B D
E F G I K
L P Q S T
U V W X Z
```
##### Step 2: Prepare the Plaintext
- Remove spaces and punctuation from the plaintext: "PLEASET RANSF ERONEM ILLIOND OLLAR"
##### Step 3: Break Plaintext into Pairs
- Break the prepared plaintext into pairs of characters (digraphs):
	``` PL EA SE TR AN SF ER ON EM IL LI ON DO LX LA RX ```
##### Step 4: Adjust for Identical Letters
- Replace any pairs containing identical letters with "X":
	``` PL EA SE TR AN SF ER ON EM IL LI ON DO LX LA RX ```
##### Step 5: Apply Playfair Cipher
Encrypt each pair of characters using the Playfair grid:
$$\large pl \rightarrow qp \qquad \qquad ea \rightarrow im \qquad \qquad se \rightarrow li \qquad \qquad tr \rightarrow zd \qquad \qquad an \rightarrow ra$$
$$\large sf \rightarrow pi \qquad \qquad er \rightarrow km \qquad \qquad on \rightarrow na \qquad \qquad em \rightarrow lc \qquad \qquad il \rightarrow es$$
$$\large li \rightarrow se \qquad \qquad on \rightarrow na \qquad \qquad do \rightarrow hr \qquad \qquad lx \rightarrow su \qquad \qquad la \rightarrow sm$$
$$\large rx \rightarrow az$$
$$\large c.t = qp \ im \ li \ zd \ ra \ pi \ km \ na \ lc \ il \ es \ se \ na \ hr \ su \ sm \ az$$

<hr>

### 03) Monoalphabetic Cipher: Reversed Alphabet 🔄

- A `monoalphabetic cipher` is a type of substitution `cipher` where each letter in the plaintext is consistently replaced with another letter throughout the entire message. 
- In this case, we'll explore a `monoalphabetic cipher` where the characters are replaced with their `corresponding characters` from the `reversed alphabet`.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
z y x w v u t s r q p o n m l k j i h g f e d c b a
```
#### Encryption Process 🛠️:
To encrypt a message using the `reversed alphabet monoalphabetic cipher`:
1. Each letter in the plaintext is replaced with its corresponding letter from the reversed alphabet.
2. For example, `'a'` would be replaced with `'z'` and `'b'` with `'y'`.
#### Example 📝:
Let's take the plaintext `"hello"` as an example:
##### Encryption:
- 'h' is replaced by 's'
- 'e' is replaced by 'v'
- 'l' is replaced by 'o'
- 'l' is replaced by 'o'
- 'o' is replaced by 'l'

So, the encrypted ciphertext for "hello" using the reversed alphabet monoalphabetic cipher is "svool".

<hr>

### 04) Vigenère Cipher 🔑

- The Vigenère Cipher is a polyalphabetic substitution cipher, which means it uses multiple alphabets to encrypt the plaintext. 
- It is considered more secure than monoalphabetic ciphers because it uses a keyword to determine the shifting of letters in the plaintext. 
- Each letter in the keyword corresponds to a shift value, and these shift values are used cyclically as the encryption key.
#### Encryption Process 🛠️:
1. **Key Preparation:**
   - Choose a keyword, such as "KEYWORD", to determine the shifts.
   - Convert the keyword to numerical values using the alphabet and numbering them from 0 to 25.
     ```
     A B C D E F G H I J K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
     0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
     ```
   - For example, "KEYWORD" becomes [10, 4, 24, 22, 14, 17, 3].

2. **Encryption:**
   - For each letter in the plaintext:
     - Determine its numerical value.
     - Use the corresponding shift value from the keyword.
     - Add the numerical value of the plaintext letter to the shift value modulo 26.
     - Convert the resulting numerical value back to a letter.

3. **Decryption Process:**
   - Similar to encryption but subtract the shift value from the ciphertext instead.
#### Example 📝:
- Let's encrypt the plaintext "WE ARE DISCOVERED. SAVE YOURSELF" using the keyword "KEYWORD":

```
22 4   0  17 4    3  8  18 2  14 21 4  17 4  3    18 0  21 4    24 14 20 17 18 4  11 5
W  e - a  r  e  - d  i  s  c  o  v  e  r  e  d. - s  a  v  e  - y  o  u  r  s  e  l  f
10 4   24 22 14   17 3  10 4  24 22 14 17 3  10   4  24 22 14   17 3  10 4  24 22 14 17 
k  e - y  w  o  - r  d  k  e  y  w  o  r  d  k. - e  y  w  o  - r  d  k  e  y  w  o  r
---------------------------------------- Addition --------------------------------------
32 8 - 24 39 18 - 20 11 28 6  38 43 18 34 7  13 - 22 24 43 18 - 41 17 30 21 42 26 25 22
---------------------------------------- mod 26 ----------------------------------------
6  8 - 24 13 18 - 20 11 2  6  12 17 18 8  7  13 - 22 24 17 18 - 15 17 6  21 16 0  25 22
g  i - y  n  s  - u  l  c  g  m  r  s  i  h  n  - w  y  r  s  - p  r  g  v  q  a  z  w
```

- **Plaintext:**           "we are discovered. save yoursrlf"
- **Encrypted Text:** "gi  yns ulcgmrsihn. wyrs prgvqazw"

<hr>

### 05) Vernam Cipher: 🛡️

- The Vernam Cipher is a **symmetric encryption** algorithm where each bit of the plaintext is XORed (⊕) with the corresponding bit of a randomly generated key to produce the ciphertext.
- It provides **perfect secrecy** when the key is truly random, has the same length as the plaintext, and is never reused. 🔒

```
XOR, or exclusive OR, is a logical operation that compares two bits. It returns true (1) if the bits are different and false (0) if they are the same.
```
#### Encryption Process:
1. Generate a random key with the same length as the plaintext.
2. Represent both the plaintext and the key in binary form as 5 bits. 📊
3. Apply the XOR (⊕) operation between each bit of the plaintext and the corresponding bit of the key.
4. The result of the XOR (⊕) operation becomes the ciphertext. 🔑
#### Example:
- Let's encrypt the plaintext `"HELLO"` using the key `"PLUTO"`.

```
A B C D E F G H I J K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
```

```
Plaintext:   H     E     L     L     O
Number:      7     4     11    11    14
Binary:    00111 00100 01011 01011 01110

Key:         P     L     U     T     O
Number:      15    11    20    19    14
Binary:    01111 01011 10100 10011 01110

XOR:       01000 01111 11111 11000 00000
Number:      8     15    31    24    0
Ciphertext:  I     P     F     Y     A
```

<hr>

### 06) Polyalphabetic Cipher:

#### Explanation:
- The Polyalphabetic Cipher is a type of encryption where multiple substitution alphabets are used. 
- It improves upon the monoalphabetic cipher by employing a keyword to determine the shifting of letters in the plaintext, making it more secure.
- Each letter in the plaintext is shifted by a different amount according to the corresponding letter in the keyword.
- **Encryption Equation:**  $\large c_i = (p_i + k)\ \% \ n$
- **Decryption Equation:**   $\large p_i = (c_i - k)\ \% \ n$

#### Encryption Process:
1. Choose a keyword, such as "SECURITY", to determine the shifts.
2. Represent the plaintext and the keyword as numerical values using the alphabet (A=0, B=1, ..., Z=25).
3. Apply each letter of the keyword cyclically to the plaintext, shifting each letter according to its numerical value.
4. Add the numerical value of the corresponding keyword letter to the numerical value of the plaintext letter, modulo 26, to get the numerical value of the ciphertext letter.
5. Convert the numerical value of the ciphertext letter back to a letter using the alphabet.

#### Example:
Let's encrypt the plaintext "WE ARE DISCOVERED" using the keyword "SECURITY".
```
A B C D E F G H I J K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
```

```
Plaintext:       W  E  A  R  E  D  I  S  C  O  V  E  R  E  D
Number:          22 4  0  17 4  3  8  18 2  14 21 4  17 4  3
Keyword:         S  E  C  U  R  I  T  Y  S  E  C  U  R  I  T
Shift (Number):  18 4  2  20 17 8  19 24 18 4  2  20 17 8  19
------------------------------------- Addition and % -----------------------------------
Ciphertext:      14 8  2  11 21 11 1  16 20 18 23 24 8  12 22
Converted:       O  I  C  L  V  L  B  Q  U  S  X  Y  I  M  W
```

<hr>

### 07) One-Time Pad Encryption: Unbreakable Security

- A theoretically unbreakable encryption method when used correctly.
- It utilizes a key that is **at least** as long as the plaintext and is **truly random**.
- **Encryption Equation:**  $\large c_i = (p_i + k)\ \% \ n$
- **Decryption Equation:**   $\large p_i = (c_i - k)\ \% \ n$
#### Example:
Let's encrypt the plaintext "ATTACK NOW" using the key "KJUIMGRTN".
```
A B C D E F G H I J K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
```

```
Plaintext:       A  T  T  A  C  K  N  O  W
Number:          0  19 19 0  2  10 13 14 22
Key:             K  J  U  I  M  G  R  T  N
Number:          10 9  20 8  12 6  17 19 13
-------------- Addition and % -------------
Ciphertext:      10 2  13 8  14 16 4  7  9
Converted:       K  C  N  I  O  Q  E  H  J
```

<hr>

### 08) Row Transposition Cipher:

- The Row Transposition Cipher is a transposition cipher where the plaintext is written out in rows of a fixed length, and then read out again `column by column`, but in a different order determined by a keyword.
- It provides a simple form of encryption by rearranging the order of the characters in the plaintext based on the given keyword.

#### Encryption Process:
1. Write the plaintext message in rows of a fixed length, filling in any unused spaces with placeholder characters.
2. Permute the columns of the rows based on the alphabetical order of the keyword, rearranging the characters according to the positions of the letters in the keyword.
3. Read the ciphertext by columns, starting with the column corresponding to the first letter in the keyword, followed by the second letter, and so on.

#### Example:
- Let's encrypt the plaintext "INFORMATION ENGINEERING" using the keyword "MEGA".
- Arrange the plaintext into rows of 4 characters each:
```
       4 2 3 1
Row 0: m e g a 
--------------
Row 1: i n f o
Row 2: r m a t
Row 3: i o n e
Row 4: n g i n
Row 5: e e r i
Row 6: n g y z
```
- Read the ciphertext by columns, starting with the column corresponding to the first letter in the keyword:
```
Ciphertext: oteniz nmogeg faniry irinen
```

<hr>

### 09) Rail Fence Cipher:

- The Rail Fence Cipher is a transposition cipher that rearranges the plaintext characters in a zigzag pattern across multiple "rails" or "rows" before reading them off for encryption.
- It provides a simple form of encryption by writing the plaintext characters in a zigzag pattern across a specified number of rows, and then reading them off in a linear fashion.
#### Encryption Process:
1. Write the plaintext characters in a zigzag pattern across the specified number of rows, called the "depth".
2. Read off the characters row by row to obtain the ciphertext.
#### Example:
Let's encrypt the plaintext "MEET ME AFTER THE TOGE PARTY" using a depth of 2.

- **Plaintext:**  M   E   E   T   M   E   A   F   T   E   R   T   H   E   T   O   G   E   P   A   R   T   Y
- **Depth:**  2
- **Zigzag Pattern:**
```
Encrypt: M  E  M  A  T  R  H  T  G  P  R  Y
           E  T  E  F  E  T  E  O  E  A  T
Ciphertext: MEMATRHTGPRYETEFETEOEAT
```

```
Ciphertext / 2: MEMATRHTGPRY / ETEFETEOEAT
Pi: M  E  M  A  T  R  H  T  G  P  R  Y
      E  T  E  F  E  T  E  O  E  A  T
```

[[Chapter 3 - Block Cipher and Data Encryption Standard (DES)]]