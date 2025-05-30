## ✅ Lecture 14: Software Security

---

### 🔎 Why Is Software Security Critical?

- **All security mechanisms (crypto, access control, etc.) are implemented in software.**
    
- If the software is **vulnerable**, attackers can bypass even the strongest cryptography.


🧨 Famous failures due to software bugs:

- **NASA Mars Lander**: $165M loss due to a metric/imperial unit conversion bug.
    
- **Denver Airport**: Buggy baggage system caused 11-month delay costing >$1M/day.
    
- **MV-22 Osprey**: Military aircraft with deadly consequences due to software issues.

---

### ⚠️ Complexity = Enemy of Security

> Quote: “Complexity is the enemy of security.” — Paul Kocher

- Modern software (e.g., Windows XP with 40+ million lines of code) is **enormously complex**, making it vulnerable.
    
- More code = more bugs = more attack surfaces.

---

## 🧵 Main Categories of Software Vulnerabilities

|Type|Details|
|---|---|
|**Unintentional (Program Flaws)**|- Buffer Overflow  <br>- Incomplete Mediation  <br>- Race Conditions|
|**Intentional (Malware)**|- Viruses  <br>- Worms  <br>- Other malicious software|

---

## 🧨 Program Flaws (Unintentional)

A **flaw** can be:

- An **error** → may cause a **fault** (internal) → may result in a **failure** (external behavior)

### Example of Buffer Error:

```c
char array[10];
for (i = 0; i < 10; ++i)
   array[i] = 'A';
array[10] = 'B'; // Error – out of bounds!
```

---

## 🔥 Buffer Overflow

### 🔁 How It Works:

1. User sends data (e.g., via web form)
    
2. Server puts it in a fixed-size buffer (like an array)
    
3. Data **exceeds** buffer size
    
4. Extra data **overwrites** other parts of memory
    
    - May overwrite **return address** or **auth flags**

### ☠️ Dangerous Outcome:

- Attacker can **inject code** and gain control of system execution.

---

## 📦 Memory Layout (Simplified)

|Segment|Purpose|
|---|---|
|Text|Code|
|Data|Static variables|
|Heap|Dynamic memory (e.g., `malloc`)|
|Stack|Function parameters, local variables, return address|

- **Stack grows down**, **heap grows up**.

---

### 🧬 Stack Smashing

- A type of buffer overflow that **overwrites the return address** on the stack.
    
- Attacker injects “evil code” and **redirects execution** to that code.
    
- To succeed:
    
    - Overwrite `ret` with the correct **address**
        
    - Use **NOP sleds** to increase success chance


📚 Famous article: _Smashing the Stack for Fun and Profit_ – Aleph One

---

## 🛡️ Defenses Against Stack Smashing

|Technique|How It Helps|
|---|---|
|**NX Bit** (No Execute)|Makes stack non-executable|
|**Canary Values**|Placed before return address; if changed, exit program|
|**Safe Languages**|Java, Python, C# (no direct memory access)|
|**Safe C Functions**|e.g., `strncpy` instead of `strcpy`|
|**ASLR** (Address Space Layout Randomization)|Randomizes memory layout to confuse attacker|

🕊️ But still not foolproof — attackers may **bypass or de-randomize** these protections.

---

## 🧪 Incomplete Mediation

Occurs when software **fails to validate input** properly.

### 🔁 Real Examples:

- Form allows date of birth `1980-04-31` (invalid date)
    
- SQL injection: `' ; DROP DATABASE users; --`


🛡️ **Validate everything** (on both **client and server** sides). Never trust client-side validation alone.

---

## ⚔️ Race Conditions

- Happen when a **security-critical process** occurs in **multiple stages**
    
- Attacker **interferes** between these stages.

### 🧵 mkdir Example (UNIX):

1. Allocate space
    
2. User inserts symbolic link to a protected file
    
3. System assigns ownership to wrong file

🛡️ Fix: Ensure **atomicity** — the entire operation must happen **as a single step**.

---

## 📚 Pages with Key Examples and Attacks

|Topic|Slides|
|---|---|
|Real-world software failures|3|
|Buffer Overflow Intro|10–13|
|Memory & Stack Visualization|14–18|
|Code Injection Mechanism|19–25|
|Buffer Overflow Attack Steps|22–26|
|Stack Defenses (Canary, ASLR)|28–33|
|Incomplete Mediation|34–39|
|Race Conditions & mkdir attack|40–44|

---

## ✅ Final Takeaways

- **Software is the weakest link** in most security systems.
    
- **Buffer overflows** remain a top threat despite decades of defenses.
    
- You **must validate all inputs** and ensure secure coding practices.
    
- Think like an attacker, **defend like an engineer**.