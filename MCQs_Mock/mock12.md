## ✅ GJU-Style MCQs – Lecture 12: **Symmetric Key Cryptography**

---

### **1. In symmetric key cryptography, which of the following is true?**

A) The same key is used for encryption and decryption  
B) It uses public and private key pairs  
C) It is only used for digital signatures  
D) Key distribution is not required

> **Answer:** A) The same key is used for encryption and decryption

---

### **2. What is the block size of DES (Data Encryption Standard)?**

A) 56 bits  
B) 48 bits  
C) 64 bits  
D) 128 bits

> **Answer:** C) 64 bits  
> _Note:_ DES uses a 56-bit key, but encrypts 64-bit blocks.

---

### **3. How many rounds are used in DES encryption?**

A) 8  
B) 10  
C) 16  
D) 32

> **Answer:** C) 16

---

### **4. What is the size of the effective DES key used after removing parity bits?**

A) 64 bits  
B) 48 bits  
C) 32 bits  
D) 56 bits

> **Answer:** D) 56 bits

---

### **5. The main purpose of the Feistel function in DES is to:**

A) Generate keys for encryption  
B) Perform compression  
C) Provide confusion and diffusion using substitution and permutation  
D) Digitally sign the message

> **Answer:** C) Provide confusion and diffusion using substitution and permutation

---

### **6. In Triple DES, encryption is performed using:**

A) One DES key used three times  
B) Three DES encryptions with one key  
C) Two or three keys used in EDE mode  
D) AES run three times

> **Answer:** C) Two or three keys used in EDE (Encrypt-Decrypt-Encrypt) mode

---

### **7. Which of the following statements is true about AES?**

A) It uses a 64-bit block size  
B) It uses a Feistel structure  
C) It supports only 128-bit keys  
D) It uses a substitution-permutation network (SPN)

> **Answer:** D) It uses a substitution-permutation network (SPN)

---

### **8. AES-256 uses how many rounds of encryption?**

A) 10  
B) 12  
C) 14  
D) 16

> **Answer:** C) 14

---

### **9. In ECB mode (Electronic Codebook), what is a major weakness?**

A) It uses a different key per block  
B) Identical plaintext blocks result in identical ciphertext blocks  
C) It requires padding  
D) It cannot be parallelized

> **Answer:** B) Identical plaintext blocks result in identical ciphertext blocks

---

### **10. Which block cipher mode is most suitable for parallel processing?**

A) CBC  
B) OFB  
C) CFB  
D) CTR

> **Answer:** D) CTR (Counter Mode)

---

### **11. Cipher Block Chaining (CBC) mode prevents pattern visibility by:**

A) Using a different key for each block  
B) Randomizing key sizes  
C) XORing each plaintext block with the previous ciphertext block  
D) Reversing bit order in each block

> **Answer:** C) XORing each plaintext block with the previous ciphertext block

---

### **12. Which DES mode of operation converts a block cipher into a stream cipher?**

A) ECB  
B) CBC  
C) OFB  
D) CFB

> **Answer:** C) OFB (Output Feedback)

---

### **13. Which of the following is the biggest challenge in symmetric key cryptography?**

A) Encryption speed  
B) Hash generation  
C) Secure key distribution  
D) Message integrity

> **Answer:** C) Secure key distribution

---

### **14. What is the role of the P-box in DES?**

A) Performs substitution  
B) Permutes bits to spread influence (diffusion)  
C) Compresses the key  
D) Generates random bits

> **Answer:** B) Permutes bits to spread influence (diffusion)

---

### **15. Which part of DES increases key confusion by substituting 6-bit inputs with 4-bit outputs?**

A) Expansion box  
B) Key schedule  
C) S-boxes  
D) XOR gate

> **Answer:** C) S-boxes