## ✅ Lecture 13: Public Key Cryptography & Information Hiding

---

### 🔐 1. Public Key Cryptography (Asymmetric Crypto)

- **Two keys**: One to **encrypt**, one to **decrypt**
    
- Example:
    
    - Alice encrypts using Bob’s **public key**
        
    - Only Bob can decrypt it using his **private key**

#### 🔑 Key Concepts:

- Based on **trapdoor one-way functions**:
    
    - Easy to compute in one direction (e.g., N = p × q)
        
    - Hard to reverse (e.g., find p and q from N)
        
- Common use: **encryption**, **digital signatures**, **authentication**

---

### ✍️ 2. Digital Signature

- Bob signs by encrypting with his **private key**
    
- Anyone can verify the signature by decrypting with Bob’s **public key**

✅ Ensures **authenticity** and **non-repudiation**  
❌ Not possible with symmetric key crypto (see example in slides 12–13)

---

### 🔄 3. Diffie-Hellman Key Exchange

Used to establish a **shared symmetric key**, not for encrypting data directly.

#### Process:

1. Alice and Bob agree on public numbers `p` (prime) and `g` (generator)
    
2. Alice picks secret `a`, sends `g^a mod p` to Bob
    
3. Bob picks secret `b`, sends `g^b mod p` to Alice
    
4. Both compute the same shared key:  
    `K = g^ab mod p`

✅ No private key is shared  
❌ Vulnerable to **Man-in-the-Middle (MiM)** attack

---

### 📌 4. Uses for Public Key Cryptography

|Purpose|Details|
|---|---|
|**Confidentiality**|Secure communication over untrusted networks|
|**Authentication**|Verifying identities|
|**Digital Signatures**|Proves origin and integrity (non-repudiation)|

---

### 🚫 5. Non-Repudiation vs Symmetric MAC

- MAC (Message Authentication Code) using symmetric key **does not** offer non-repudiation:
    
    - Both sender and receiver know the key → no proof of origin

✅ With **digital signature**, only the **private key holder** could’ve signed

---

### 🧾 6. Public Key Notation

|Operation|Notation|
|---|---|
|Sign with Alice’s private key|`[M]Alice`|
|Encrypt with Alice’s public key|`{M}Alice`|
|Sign then Encrypt|`{[M]Alice}Bob`|
|Encrypt then Sign|`[{M}Bob]Alice`|

Both achieve **confidentiality + integrity**, but **order may impact trust flow**.

---

### 🏢 7. Public Key Infrastructure (PKI)

Used to verify public key ownership via **digital certificates**.

#### Certificate Authority (CA):

- Trusted entity that **signs** certificates
    
- Verifies that a public key belongs to a specific user
    
- Common format: **X.509**

---

### 🧱 8. PKI Trust Models

|Model|Description|
|---|---|
|**Monopoly**|Single CA trusted by all|
|**Oligarchy**|Few CAs (used in web browsers today)|
|**Anarchy**|“Web of trust” (used in PGP); trust decisions are decentralized|

⚠️ Security risk if CA is compromised

---

### 🔐 9. Symmetric vs Public Key (Comparison)

|Type|Pros|Cons|
|---|---|---|
|Symmetric|Fast, no PKI needed|Key distribution challenge|
|Public Key|Supports signatures, no key sharing|Slower, needs PKI|

✅ Best practice: Use **hybrid crypto**

- Public key crypto to **exchange symmetric key**
    
- Symmetric key crypto to **encrypt the data**

---

### 🕵️ 10. Information Hiding Techniques

---

#### 🔍 A. Digital Watermarking

- Embeds invisible or visible info into media (images, music, documents)

|Type|Description|
|---|---|
|**Visible**|Mark clearly shown (e.g., “CONFIDENTIAL”)|
|**Invisible**|Hidden, used to trace or verify|
|**Robust**|Survives attacks or modification|
|**Fragile**|Breaks under tampering (used for integrity checks)|

✅ Can help trace leaks or detect tampering  
❌ Can be removed using watermark-removal tools (e.g., Stirmark)

---

#### 🧙‍♂️ B. Steganography

- Hiding **secret messages** inside regular files (e.g., images or HTML)

#### Example:

- Modify **low-order RGB bits** in an image
    
    - Human eye can’t detect the change
        
    - Computer can extract the hidden message

##### HTML Stego Example:

- Slight color code changes (`#000000` vs `#000101`) used to encode bits
    
- Viewer sees same webpage, but data is encoded in color values

✅ Undetectable by casual observers  
❌ Can be fragile & detectable with forensic tools

---

## ✅ Key Takeaways for Exam

|Concept|Summary|
|---|---|
|**Public Key Crypto**|Uses two keys; enables signatures and secure key exchange|
|**Digital Signature**|Ensures authenticity and non-repudiation|
|**Diffie-Hellman**|Key exchange algorithm; no encryption/signing|
|**PKI**|Infrastructure for verifying public keys via trusted CAs|
|**Watermarking**|Embeds ownership or integrity marks in media|
|**Steganography**|Hides data in images/text using imperceptible changes|

---

## 📚 Pages with Important Examples and Diagrams

| Topic                            | Slides |
| -------------------------------- | ------ |
| Diffie-Hellman exchange          | 4–9    |
| Non-repudiation vs MAC           | 12–13  |
| Sign + Encrypt vs Encrypt + Sign | 15–18  |
| PKI and certificate structure    | 20–25  |
| Real-world hybrid encryption     | 29     |
| Watermarking + examples          | 32–35  |
| Steganography & HTML encoding    | 36–42  |
