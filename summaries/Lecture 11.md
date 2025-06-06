## ✅ Lecture 11: Cryptography – Summary & Explanation

---

### 🧠 1. Introduction to Cryptography

**Cryptology** = Cryptography (making secret codes) + Cryptanalysis (breaking them)

- **Cryptography**: Making encrypted messages
    
- **Cryptanalysis**: Decrypting without knowing the key
    
- **Kerckhoffs’ Principle**: Assume the **system is known**, but the **key is secret**

---

### 🔐 2. Key Terminology

|Term|Meaning|
|---|---|
|**Plaintext**|Original readable message|
|**Ciphertext**|Encrypted unreadable message|
|**Key**|A secret used to encrypt/decrypt|
|**Symmetric Key**|Same key for encryption and decryption|
|**Asymmetric Key**|Public key (encrypt), Private key (decrypt)|

---

### ⚙️ 3. Substitution Ciphers

#### 🔸 Caesar Cipher (Shift Cipher)

- Each letter is shifted by a fixed number (e.g. +3)
    
- `a → D`, `b → E`, `c → F`, …
    

#### 🔸 Example:

- **Plaintext**: `fourscoreandsevenyearsago`
    
- **Ciphertext** (shift by 3): `IRXUVFRUHDQGVHYHQBHDUVDJR`

#### 🔓 Decryption:

- Just reverse the shift using the key

---

### 🔍 4. Cryptanalysis (Attacks)

#### Method 1: **Exhaustive Search**

- Try all 26 Caesar shifts

#### Method 2: **Frequency Analysis**

- Match letter frequency of ciphertext with English letter frequencies
    
- Common letters: E, T, A, O, I, N…

---

### 🧠 5. Substitution (General Case)

- Not limited to shifting — you can map each letter to **any other**
    
- Total possible keys: **26! ≈ 2.88 × 10²⁶**
    
- Example:
    
    - `a → J`, `b → I`, ..., `z → O`
        

---

### 🔎 6. Frequency Analysis – Steps

1. Count letter frequencies in ciphertext
    
2. Compare with expected English frequencies
    
3. Use pattern recognition (e.g., `THE`, `AND`)
    
4. Refine guesses iteratively

✅ Powerful for **monoalphabetic** ciphers, weaker for **poly** ciphers.

---

### 🔁 7. Vigenère Cipher (Polyalphabetic Cipher)

- Uses a **keyword** to determine shifting pattern
    
- Repeats keyword over plaintext

#### Example:

- Keyword: `CAT` → shifts: 2, 0, 19
    
- Plaintext: `attackatdawn`
    
- Ciphertext: `ctmccdctwcwg`

🔓 Harder to break than Caesar Cipher due to varying shifts.

---

### 🔐 8. Playfair Cipher

- Encrypts **pairs of letters** using a 5x5 matrix
    
- `I` and `J` treated the same
    
- Used in WWI

#### Steps:

1. Break into pairs (e.g., `hello` → `he lx lo`)
    
2. Apply matrix rules (same row, column, or rectangle)
    
3. Example: `he → KG`, `lx → YV`

---

### 🔄 9. Transposition Ciphers

#### A. **Rail Fence Cipher**

- Rearrange letters by writing in "rails" (rows)

**Plaintext**: `This is a secret message`  
**Rails = 2**  
**Ciphertext**: `TIIAERTESGHSSSCEMSAE`

#### B. **Double Transposition**

- Apply 2 permutations (row and column)
    
- Stronger than single transposition

---

### 💣 10. One-Time Pad (OTP)

- Use a random key **as long as the message**
    
- XOR the plaintext with key

✅ **Provably secure**  
❌ Key must be random, used once, and shared securely

**Used in WWII (VENONA Project)**: USSR encrypted atomic bomb data

---

### 📖 11. Codebook Cipher

- Words replaced by code numbers
    
- Often used with **additive pad** to make it harder to decrypt

#### Example:

- `Frieden` → `17142`
    
- Ciphertext = Codebook value + Random additive

**Zimmerman Telegram** (WWI): Famous intercepted message

---

### 🧠 12. Historical Context

|Event|Description|
|---|---|
|**Zimmerman Telegram**|Led U.S. to WWI|
|**VENONA**|U.S. decoded Soviet spy messages|
|**WWII Enigma**|Broken by Allies (Bletchley Park)|

---

### 📊 13. Claude Shannon – Theoretical Foundations

- Father of **Information Theory**
    
- Key concepts:
    
    - **Confusion**: Obscure relationship between key & ciphertext
        
    - **Diffusion**: Spread plaintext across ciphertext
        
- Proved **One-Time Pad is secure**

---

### 🔧 14. Types of Cryptography

|Type|Details|
|---|---|
|**Symmetric Key**|Same key for both directions (e.g. AES)|
|**Public Key**|Two keys: public/private (e.g. RSA)|
|**Hash Algorithms**|One-way mapping (e.g. SHA-256)|

---

## ✅ Key Takeaways for the Exam

|Concept|Description|
|---|---|
|Caesar Cipher|Shift by fixed number (easy to break)|
|Frequency Analysis|Used to crack monoalphabetic ciphers|
|Vigenère Cipher|Harder, uses repeating key shifts|
|Playfair Cipher|Encrypts letter pairs using matrix|
|Transposition Cipher|Rearranges letter positions|
|One-Time Pad (OTP)|Unbreakable if used correctly|
|Codebook Cipher|Word → number + additive|
|Shannon's Theory|Confusion & diffusion = secure cipher|
|Symmetric vs Asymmetric|One vs two keys|

---

## 📚 Pages with Examples for Practice

|Topic|Pages|
|---|---|
|Caesar Cipher Example|Slides 6–7|
|Exhaustive Search|Slide 9|
|Frequency Analysis|Slides 13–15|
|Vigenère Cipher|Slides 17–18|
|Playfair Cipher|Slides 19–21|
|Transposition Ciphers|Slides 22–23|
|One-Time Pad|Slides 24–30|
|Codebook & Zimmerman|Slides 31–34|
|Election 1876 Example|Slides 35–36|
|Claude Shannon & AES|Slides 38–40|