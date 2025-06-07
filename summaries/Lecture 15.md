## ✅ Lecture 15: SQL Injection (SQLi)

---

### 🔎 What is SQL Injection?

- **SQL Injection = a type of attack** that exploits **vulnerabilities** in software that interacts with a database.
    
- Happens when untrusted user input is **inserted directly into SQL queries** without proper validation.

---

### ⚔️ The SQL Injection Attack

- SQL (Structured Query Language) is used to access databases.

#### ✅ Normal Query:

```sql
SELECT CBalance FROM Balances WHERE Acct='1234';
```

#### ❌ Injected Input:

If the input is:

```bash
' OR '1'='1
```

Then the query becomes:

```sql
SELECT CBalance FROM Balances WHERE Acct='' OR '1'='1';
```

Since `'1'='1'` is always **true**, this returns **all rows**.

---

## 🧪 SQL Injection Example Program

```php
$acct = $_GET['account'];
$query = "SELECT CBalance FROM Balances WHERE Acct='$acct'";
```

#### Input:

```bash
9999' OR '1'='1
```

#### Becomes:

```sql
SELECT CBalance FROM Balances WHERE Acct='9999' OR '1'='1';
```

This bypasses intended checks and gives unauthorized access to sensitive data.

---

## 🧠 Real Database Example (Accounts + Balances)

|Account|Name|CBalance|
|---|---|---|
|1234|Joe B|67.84|
|6787|Tom M|99.21|

Attackers can extract info from both tables using injected queries.

---

## 💣 Attack Techniques

### 🔍 Guessing Table and Field Names

- Try inputs like:
    
    - `acct=NULL`
        
    - `userid=NULL`
        
    - `SELECT COUNT(*) FROM users`
        
- Errors help reveal field/table names.

### 🧩 UNION-Based Attacks

- Combines results from two queries:

```sql
SELECT name, userid FROM accounts 
UNION SELECT account, cbalance FROM balances;
```

- Must match **column count** and **types** on both sides of `UNION`.

### 🔄 ORDER BY Attack

- Helps identify column count:

```sql
' ORDER BY 1 --  (works)
' ORDER BY 3 --  (error: column 3 not found)
```

---

## 🧨 Batched SQL Attacks

SQL allows **multiple statements** in one line:

```sql
SELECT * FROM Users WHERE UserId = 105; DROP TABLE Suppliers;
```

Other attack types:

- `INSERT` (to add malicious data)
    
- `UPDATE` (to modify values)

---

## 🔐 Defenses Against SQL Injection

---

### ✅ 1. Input Validation

- **Whitelisting** is better than blacklisting
    
- Check:
    
    - Correct length?
        
    - Correct type?
        
    - Correct format? (e.g., regex)

#### Example:

```php
$zip_re = '/^\d{5}([-\s]\d{4})?$/';
if (! preg_match($zip_re, $zip)) {
    error("Incorrect zip code format");
}
```

---

### ✅ 2. Prepared Statements (Best Practice)

- Prevents SQLi by **separating SQL logic from data values**.
    
- Variables are passed safely to the DB engine.

#### PHP:

```php
$stmt = $con->prepare("SELECT * FROM users WHERE name=? AND pass=?");
$stmt->execute([$name, $pass]);
```

#### Python:

```python
cursor.execute("SELECT * FROM table WHERE a=%s", (val,))
```

#### Java:

```java
PreparedStatement stmt = conn.prepareStatement("SELECT * FROM table WHERE id=?");
stmt.setInt(1, userId);
```

---

### ✅ 3. Escaping Input (Not Foolproof)

- Escape characters like:
    
    - `'` → `\'`, `"` → `\"`
        
- Use functions like:

```php
mysql_real_escape_string($input);
```

⚠️ Not as secure as prepared statements.

---

### ✅ 4. Additional Defenses

- **Limit database privileges**:
    
    - Don't use DB admin credentials in the app.
        
    - Use read-only accounts for SELECT-only queries.
    
- **Disable detailed error messages**:
    
    - Avoid exposing DB names, fields, or SQL syntax in browser errors.
    
- **Scan for bad keywords** like `DROP`, `INSERT`, `UPDATE`, etc.
    
- **Set length limits** for inputs.
    
- **Centralize input validation** in one place for easier auditing.

---

## 📚 Pages with Examples & Code

|Topic|Slide(s)|
|---|---|
|SQL Injection Intro & Example Query|2–7|
|PHP Sample Code|8–9|
|Sample Attacks & Guessing Techniques|10–16|
|Batched SQL & UNION Attacks|17–23|
|Defenses: Input Validation|24–27|
|Defenses: Prepared Statements (PHP, Java, Python)|28–31|
|Escaping Strings & More Defenses|32–35|

---

## ✅ Final Summary

- SQL Injection exploits bad coding practices, especially **unvalidated inputs** and **inline SQL queries**.
    
- It can lead to data theft, corruption, and even **full control** of the system.
    
- Use **prepared statements** + **input validation** + **least privilege**.
    
- Never trust user input — always sanitize, validate, and prepare.