### ✅ **Lecture 17 Summary – Malware & Software-Based Attacks**

---

### 🔐 **1. What Is Malware?**

Malware stands for _malicious software_ — it’s any software designed to harm, exploit, or disable systems.

#### 📌 **Types of Malware**:

|Type|Description|
|---|---|
|**Virus**|Passively spreads by attaching to files|
|**Worm**|Actively spreads across networks|
|**Trojan Horse**|Looks legitimate but contains malware|
|**Trapdoor**|Secret entry for unauthorized access|
|**Rabbit**|Rapid replication to drain resources|
|**Spyware**|Secretly collects user info|

---

### 🧬 **2. Where Do Viruses Hide?**

Viruses can live in:

- Boot sectors (executes before OS starts)
    
- Memory (resident)
    
- Applications/macros
    
- Libraries, compilers, even antivirus tools

---

### 🦠 **3. Famous Malware Examples**

|Name|Year|Details|
|---|---|---|
|**Brain**|1986|First known virus, boot sector infection|
|**Morris Worm**|1988|Buffer overflows, password guessing; buggy—overloaded systems|
|**Code Red**|2001|Exploited MS IIS; spread fast and launched DDoS|
|**Slammer**|2004|Infected 75k systems in 10 mins, 376-byte payload|
|**Botnets**|Now|Networks of infected devices (e.g., via IRC or P2P)|

---

### 🐴 **4. Trojan Horse Attacks**

- Hidden malware disguised as useful software
    
- Example: Fake MP3 file that opens iTunes but does malicious activity in the background

---

### 🔍 **5. Malware Detection Techniques**

#### a. **Signature Detection**

- Checks for specific bit patterns in files
    
- Accurate for known malware
    
- Downside: can't detect new/unknown threats

#### b. **Change Detection**

- Hash files and check if they change over time
    
- Very accurate, but can have false alarms and is resource-intensive

#### c. **Anomaly Detection**

- Detects abnormal behavior (e.g., unexpected traffic or file changes)
    
- Can catch unknown malware but prone to false positives

---

### 🔮 **6. Evolving Malware Techniques**

|Method|Description|
|---|---|
|**Encrypted Viruses**|Use encryption to hide code|
|**Polymorphic Malware**|Encrypts payload + morphs decryptor|
|**Metamorphic Malware**|Completely rewrites its code on each infection|
|**Warhol Worm**|Hypothetical fast-spreading worm|
|**Flash Worm**|Instant infection using precompiled IP hit-list|

---

### 🛡️ **7. Defense Techniques**

- **Patch Management:** Apply updates before malware exploits known bugs
    
- **IDS/IPS:** Intrusion detection/prevention systems
    
- **White Worms:** Good worms that patch or immunize systems (not common due to ethics)
    
- **Rate Limiting:** Reduces how fast malware can spread

---

### ↔️ **8. Push vs Pull Malware**

- **Push**: Malware forces itself into systems (e.g., worms)
    
- **Pull**: Victim downloads it unknowingly (e.g., phishing, fake updates)

✅ **Defenses**: Web filters, browser updates, antivirus, ad blockers, user awareness

---

### 🤖 **9. Botnets**

- Infected “bots” controlled by a botmaster
    
- Used for spam, DDoS, identity theft, etc.
    
- Control via IRC (centralized) or P2P (harder to stop)

---

### 💡 **10. Future of Detection**

- Too many malware variants exist
    
- Idea: use a **whitelist** approach — only allow known good software

---

### 🧨 **11. Miscellaneous Software Attacks**

#### a. **Salami Attack**

- Slices off tiny, unnoticeable amounts of money (e.g., banking interest fractions)
    
- Hard to detect without oversight
    
- **Prevention**: Separation of duties, code review, automated auditing

#### b. **Linearization Attack**

- Exploits timing in system checks to guess values one step at a time
    
- Example: serial number guessing character-by-character
    
- **Prevention**: Constant-time checks

#### c. **Time Bomb**

- Logic bomb that activates at a specific time/date
    
- Example: disgruntled employee who deleted company files on a set date

---

### 📘 **Examples Found On These Slides:**

- **Brain Virus** – Slide 5
    
- **Morris Worm & Spread** – Slides 6–9
    
- **Code Red** – Slides 11–12
    
- **SQL Slammer** – Slides 13–14
    
- **MP3 Trojan** – Slides 15–17
    
- **Signature Detection Example** – Slide 19
    
- **Warhol/Flash Worm** – Slides 31–35
    
- **Botnet Infection & Control** – Slides 39–40
    
- **Salami Attack** – Slides 44–45
    
- **Linearization Serial Guessing** – Slides 46–50
    
- **Time Bomb Case Study** – Slides 51–52