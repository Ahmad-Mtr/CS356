## ✅ Lecture 16: Secure Software Development

---

### 🔧 **Penetrate and Patch Model** (Slides 2–5)

- **Definition**: Build fast → release → fix flaws later.
    
- Common in software industry due to:
    
    - Pressure to be **first to market**.
        
    - **Low liability** for security failures.
        
    - Users follow the **market leader**, even if flawed.


🧨 **Problem**:

- Patching rarely leads to secure software.
    
- Patches often **introduce new bugs**.
    
- Software constantly changes: new versions, features, environments.

---

## 🆚 Open vs Closed Source (Slides 6–10)

### 🔓 Open Source

- Source code is public (e.g., Linux).
    
- Claims:
    
    - More eyes = fewer bugs (Kerckhoffs’ Principle).
        
    - Community audits = better security.
    
- Reality:
    
    - Most users **don’t audit code**.
        
    - Attackers can **also inspect**.
        
    - Example: **wu-ftp** (8k lines, flawed after 10 years).


### 🔒 Closed Source

- Code hidden (e.g., Windows).
    
- Claims:
    
    - Security by obscurity.
    
- Reality:
    
    - Hackers reverse engineer anyway.
        
    - **Obscurity ≠ security**.


✅ **Conclusion**:

- **Development practice** matters more than open vs closed.

---

## 🧪 Software Security Testing (Slides 11–12)

> Security is harder than reliability.

- Good developers must find **almost all bugs**.
    
- Attackers only need **1 exploitable bug**.

### Example:

- If 1 bug is found every **1,000 hours**, even **10,000 hours of testing** finds just **1%** of all bugs.

---

## 🏗️ Software Development Lifecycle (Slides 13–15)

Steps:

1. Specify
    
2. Design
    
3. Implement
    
4. Test
    
5. Review
    
6. Document
    
7. Manage
    
8. Maintain

✅ Secure development needs **care at all stages** — especially up front.

---

## 🔐 Secure Design & Hazard Analysis (Slides 16–17)

### 🔧 Design:

- Prevent **high-level errors** early.
    
- Use **formal methods** (only viable in small systems).

### 🔥 Hazard Analysis Tools:

- **Attack Trees** (Schneier): Visualize all possible attack paths.
    
- **HAZOP**: Systematic analysis of risks in systems.
    
- **FMEA**: Identifies failure modes and their effects.
    
- **FTA/ETA**: Diagram-based failure analysis tools.

---

## 🔁 Peer Review (Slide 18)

3 levels:

- **Review** (informal)
    
- **Walk-through** (semi-formal)
    
- **Inspection** (formal)

✅ Effective for catching logic and code errors early.

---

## 🧪 Testing Levels & Types (Slides 19–21)

### 🔍 Levels:

- **Module testing** (small code sections)
    
- **Component testing** (few modules)
    
- **Unit testing** (multiple components)
    
- **Integration testing** (whole system)

### 🧪 Types:

- **Function** – correct outputs?
    
- **Performance** – speed, resource use?
    
- **Acceptance** – client approval?
    
- **Installation** – test install success
    
- **Regression** – after code changes

### 🔁 Other Tests:

- **Fault Injection** – simulate errors.
    
- **Bug Injection** – insert known bugs, estimate undetected bug count.

---

## 🔐 Security Testing vs Non-Security Testing (Slides 22–23)

|Security Testing|Non-Security Testing|
|---|---|
|System does what it should **and nothing else**|System does what it should|

- Exhaustive testing is **impossible**.
    
- **Hope** lies in eliminating entire bug classes (e.g., all buffer overflows).

---

## ⚙️ Configuration Management (Slide 24)

Change types:

- **Minor**: small fixes
    
- **Adaptive**: environment changes
    
- **Perfective**: enhancements
    
- **Preventive**: risk reduction

⚠️ **Any change** might introduce flaws!

---

## 🔁 Postmortem Analysis (Slide 25)

- After each security flaw:
    
    - **Analyze thoroughly**
        
    - Learn from mistakes
        
    - Prevent repeat incidents

✅ Highly underused but **critical** for security learning.

---

## 🛡️ OS-Level Security (Slides 26–41)

---

### 🔍 OS as Security Enforcer (Slides 27–30)

- OS manages memory, I/O, users, programs, etc.
    
- Ensures:
    
    - **Memory protection**
        
    - **File protection**
        
    - **Authentication**
        
    - **Authorization**

---

### 📦 Memory Protection Techniques (Slides 31–33)

|Type|Description|
|---|---|
|**Physical**|Separate hardware|
|**Temporal**|One user at a time|
|**Logical**|Sandboxing|
|**Crypto**|Encrypt data between users|

#### Implementations:

- **Base/Bounds Registers** – defines memory access range
    
- **Fence Register** – restricts memory access (static/dynamic)
    
- **Tagging** – label each memory cell (fine-grained, costly)

---

### 🔗 Segmentation (Slides 34–38)

- Divide memory into **logical segments** (e.g., code, data).
    
- OS tracks <segment, offset> and enforces protection per segment.

✅ Pros:

- Flexible access control
    
- Segment sharing between users

❌ Cons:

- Fragmentation
    
- Complexity
    
- Hard to manage dynamically growing segments

---

### 📄 Paging (Slides 39–40)

- Fixed-size segments (pages)
    
- OS handles memory via <page, offset>

✅ Pros:

- Avoids fragmentation
    
- Easier memory management

❌ Cons:

- No logical structure

---

### 🧍 Other OS Security Functions (Slide 41)

- **Authentication**: Passwords, biometrics
    
- **Authorization**: Access Control Lists (ACLs), capabilities
    
- OS is an **attractive attack target**!

---

## 📚 Key Slides for Examples and Diagrams

|Topic|Slides|
|---|---|
|Penetrate and Patch|2–5|
|Open vs Closed Source|6–10|
|Testing + Bug Injection|11–12, 19–21|
|Hazard Analysis Tools|17|
|Peer Review|18|
|Secure Design & Postmortem|16, 25|
|OS Security Functions|30–41|
|Segmentation & Paging Diagrams|34–40|

---

## ✅ Final Summary

- **Penetrate and Patch is flawed** — leads to reactive, insecure software.
    
- Open vs closed source debate misses the point: **secure practices** are key.
    
- Security testing is more demanding than regular testing — **1 bug is enough** to destroy security.
    
- OS plays a major role in enforcing isolation, authentication, and memory protections.

> **Security must be proactive**, built-in — not patched on.