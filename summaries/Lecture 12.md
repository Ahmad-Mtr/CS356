## ✅ Lecture 12: Symmetric Key Cryptography

---

### 🔐 1. What is Symmetric Key Cryptography?

- **Same key** is used for **encryption and decryption**.
    
- Both sender and receiver **must share the same secret key**.
    
- Fast and efficient—commonly used for **bulk data encryption**.

---

### 🔁 2. Block vs Stream Ciphers

|Type|Description|
|---|---|
|**Block Cipher**|Encrypts **fixed-size blocks** (e.g., 128 bits).|
|**Stream Cipher**|Encrypts **bit-by-bit** or **byte-by-byte**, like a key stream.|

---

### 🔒 3. DES (Data Encryption Standard)

- Developed in the 1970s by IBM and NIST.
    
- **Block size**: 64 bits
    
- **Key size**: 56 bits (originally 64, but 8 bits are for parity)

#### Process:

1. **Initial Permutation (IP)**
    
2. 16 rounds of processing (Feistel structure)
    
3. **Final Permutation (IP⁻¹)**

#### 🔁 Feistel Function:

Each round:

- Splits the block into `L` and `R`
    
- Applies function to `R` and combines with `L`

#### ⚠️ Security:

- Weak against brute force now.
    
- Vulnerable to **known-plaintext** and **differential attacks**

---

### 🔐 4. Triple DES (3DES)

- Applies DES **three times** with:
    
    - **Two or three different keys**
        
- Strength: ~112 bits (2-key 3DES)

#### Process:

```mathematica
Ciphertext = E(K1, D(K2, E(K1, P)))
```

✅ Stronger than DES  
❌ Slower

---

### 🔐 5. AES (Advanced Encryption Standard)

- Standard since 2001 (by NIST)
    
- **Block size**: 128 bits
    
- **Key sizes**: 128, 192, or 256 bits

#### AES Structure:

- **Substitution–Permutation Network (SPN)** (not Feistel)
    
- 10, 12, or 14 rounds depending on key size
    
- Uses **S-boxes**, **ShiftRows**, **MixColumns**, and **AddRoundKey**

✅ Strong, fast, and widely used (WiFi, HTTPS, etc.)

---

### 🔄 6. Cipher Block Modes

Used to process **messages longer than one block**.

|Mode|Description|Notes|
|---|---|---|
|**ECB (Electronic Codebook)**|Each block encrypted separately|❌ Identical plaintext = identical ciphertext|
|**CBC (Cipher Block Chaining)**|Each block XORed with previous ciphertext|✅ Hides patterns|
|**CFB (Cipher Feedback)**|Converts block cipher to stream cipher|Real-time|
|**OFB (Output Feedback)**|Key stream independent of plaintext|Resistant to errors|
|**CTR (Counter Mode)**|Uses a counter for keystream|✅ Fast & parallelizable|

---

### 🔑 7. Key Distribution Problem

Main challenge of symmetric cryptography:

> How do two parties share a secret key **securely**?

Solutions:

- **Manual exchange** (e.g., in-person)
    
- **Key Distribution Center (KDC)**: A trusted third party
    
- **Diffie-Hellman** (see asymmetric cryptography)

---

### 🧠 8. Important Concepts

- **Confusion**: Makes relationship between key and ciphertext complex
    
- **Diffusion**: Spreads plaintext influence over ciphertext

Used in:

- **DES**: Feistel structure
    
- **AES**: SPN structure

---

## ✅ Key Takeaways for Exam

|Concept|Summary|
|---|---|
|**Symmetric Key**|Same key used for encrypt/decrypt|
|**Block Ciphers**|Fixed-size chunks (e.g., DES, AES)|
|**Stream Ciphers**|Encrypt data bit-by-bit or byte-by-byte|
|**DES**|56-bit key, insecure today|
|**3DES**|Stronger than DES, uses 2–3 keys|
|**AES**|Modern, fast, secure with 128/192/256-bit keys|
|**ECB vs CBC**|ECB = weak, CBC = secure chaining|
|**CTR Mode**|Fast, parallelizable encryption|
|**Key Distribution**|Major limitation of symmetric crypto|

---

## 📚 Pages with Examples & Diagrams

|Topic|Pages|
|---|---|
|DES overview & rounds|5–10|
|Triple DES example|12|
|AES structure & operations|13–15|
|Block cipher modes|16–20|
|ECB vs CBC comparison|18|
|CTR explanation|19|
|Key distribution problem|21|