## ✅ **Lecture 17: Web Security – Summary (Simplified)**

### 🌐 **What is Web Security?**

- It's about **protecting websites and web applications** from being attacked.
    
- Focuses on **users, browsers, cookies, and data forms**.
    

---

### 🚫 **Common Web Attacks:**

#### 🧬 **Cross-Site Scripting (XSS):**

- Attacker adds **malicious scripts** to a website.
    
- Can steal cookies or personal info.
    

#### 🔁 **Cross-Site Request Forgery (CSRF):**

- Tricks users into performing actions without knowing (like deleting their own account while logged in).
    

#### 💻 **Session Hijacking:**

- Stealing someone’s **login session** (like their cookie) to act as them.
    

#### 💉 **Injection Attacks:**

- Like **SQL injection**: attacker sends bad code into a form to mess with a database.
    

---

### 🔐 **Web Security Techniques:**

- **Input Validation**: Always check and clean what users enter.
    
- **Use HTTPS**: Encrypts communication between browser and server.
    
- **Set Cookie Flags**:
    
    - `Secure`: only send over HTTPS
        
    - `HttpOnly`: can't be accessed via JavaScript
        
- **Use Tokens**: For CSRF protection
    
- **Content Security Policy (CSP)**: Controls which content (like scripts) is allowed to load
    

---

### 📖 Example Highlight:

- XSS Example: Typing `<script>alert('hacked')</script>` in a comment box that pops up alerts — this should be blocked!
    

---

### 🧩 Authentication Problems:

- Weak password storage
    
- No rate limiting on login attempts
    
- No Multi-Factor Authentication (MFA)
    

---

## 📖 Example Pages:

Look at pages **5–8** in Lecture 17 PDF for examples like:

- XSS scripts
    
- Secure cookie flags
    
- CSRF token form fields