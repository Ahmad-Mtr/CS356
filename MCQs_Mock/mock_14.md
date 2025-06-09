## ✅ GJU-Style MCQs – Lecture 14: **Software Security**

---

### **1. What is a buffer overflow?**

A) A user inputs too many fields in a form  
B) A process requests more memory than available  
C) Data written beyond the boundary of a buffer, overwriting adjacent memory  
D) When the system cache overflows

> **Answer:** C) Data written beyond the boundary of a buffer, overwriting adjacent memory

---

### **2. Which programming language is most susceptible to buffer overflow attacks?**

A) Python  
B) Java  
C) C  
D) Swift

> **Answer:** C) C  
> _Explanation:_ C does not have built-in bounds checking.

---

### **3. What is the main risk of a buffer overflow?**

A) High CPU usage  
B) Remote system crash  
C) Unauthorized code execution  
D) Data loss due to power failure

> **Answer:** C) Unauthorized code execution

---

### **4. Which of the following techniques helps prevent buffer overflow?**

A) Dynamic typing  
B) Stack canaries  
C) Base64 encoding  
D) Code minification

> **Answer:** B) Stack canaries

---

### **5. What is a common technique attackers use to exploit a buffer overflow?**

A) DNS spoofing  
B) SQL injection  
C) Return-to-libc attack  
D) Keylogging

> **Answer:** C) Return-to-libc attack

---

### **6. Which secure coding practice can help prevent many software vulnerabilities?**

A) Hardcoding credentials  
B) Avoiding comments  
C) Input validation and proper bounds checking  
D) Using global variables

> **Answer:** C) Input validation and proper bounds checking

---

### **7. What kind of attack manipulates the intended logic of a program to gain elevated access?**

A) Replay attack  
B) Privilege escalation  
C) Eavesdropping  
D) Sniffing attack

> **Answer:** B) Privilege escalation

---

### **8. In what type of injection does an attacker execute arbitrary commands on the host OS?**

A) SQL injection  
B) Code injection  
C) Command injection  
D) API injection

> **Answer:** C) Command injection

---

### **9. What is shellcode?**

A) A secure shell encryption standard  
B) Code injected by an attacker to open a shell  
C) A type of encrypted payload  
D) JavaScript used in XSS attacks

> **Answer:** B) Code injected by an attacker to open a shell

---

### **10. What is ASLR (Address Space Layout Randomization)?**

A) A type of cache flushing  
B) A technique for encoding memory  
C) A method for randomizing memory address layouts to prevent attacks  
D) A library used in secure programming

> **Answer:** C) A method for randomizing memory address layouts to prevent attacks

---

### **11. Why is disabling executable stack memory a good defense?**

A) It makes code run faster  
B) It prevents execution of injected shellcode  
C) It allows better memory reuse  
D) It improves garbage collection

> **Answer:** B) It prevents execution of injected shellcode

---

### **12. What does the “principle of least privilege” mean in software security?**

A) Allow all users maximum access  
B) Disable privileges altogether  
C) Grant users only the minimum access needed to perform their job  
D) Encrypt privileges with a key

> **Answer:** C) Grant users only the minimum access needed to perform their job

---

### **13. What is control flow integrity (CFI) used for?**

A) Making code more readable  
B) Preventing control flow hijacking attacks  
C) Avoiding syntax errors  
D) Enhancing debugging tools

> **Answer:** B) Preventing control flow hijacking attacks

---

### **14. Which of the following is the BEST way to prevent command injection in web applications?**

A) Use AES encryption  
B) Validate and sanitize user input  
C) Enable browser extensions  
D) Limit JavaScript usage

> **Answer:** B) Validate and sanitize user input

---

### **15. What type of attack is most likely if a web form sends unsanitized input directly into an SQL query?**

A) XML injection  
B) SQL injection  
C) Command injection  
D) Race condition

> **Answer:** B) SQL injection