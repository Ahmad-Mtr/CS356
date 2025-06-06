## ✅ Lecture 10: Database Security Overview

---

### 🔐 1. What Is Database Security?

Database security means **controlling who can access what data**, and **ensuring integrity, confidentiality, and availability** in large data systems. This includes:

- Managing **who has permission**
    
- **Preventing unauthorized access**
    
- **Tracking user actions**
    
- Protecting against **data leaks**, **corruption**, or **tampering**

---

### 🏗️ 2. System R Authorization Model (Discretionary Access Control)

**System R** (by IBM) is the original **DAC** model used in most relational DBMSs.

#### Main Ideas:

- Access is based on **users’ identities**
    
- Permissions granted **per object** (table/view)
    
- **Privileges**:
    
    - `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `DROP`, `INDEX`, `ALTER`
        

#### Delegation:

- Users can **grant privileges** to others using `GRANT ... WITH GRANT OPTION`.
    
- Users can **revoke privileges** using `REVOKE`.
    

---

### 🔁 3. Granting and Revoking Privileges

#### Example:

```sql
GRANT SELECT ON Employee TO Ann WITH GRANT OPTION;
REVOKE SELECT ON Employee FROM Ann;
```

#### Two revoke modes:

1. **Cascading revoke**: Removes all **privileges given through delegation**.
    
2. **Non-cascading revoke**: Prevents privilege removal if **others still rely on it**.

---

### 🔍 4. Views and Content-Based Access Control

**Views** = Virtual tables = SELECT queries that represent a subset of the real data.

Use views to:

- Show **only part of the data**
    
- Restrict access **by content**

#### Example:

```sql
CREATE VIEW Vemp AS 
SELECT * FROM Employee WHERE Salary < 20000;
GRANT SELECT ON Vemp TO Ann;
```

- If Ann tries to query this view, she'll **only see employees earning < 20k**.

✅ **Benefits**:

- Protects **sensitive data**
    
- Keeps base tables secure

---

### 🧠 5. SQL-99 Enhancements: Role-Based Access Control (RBAC)

Modern SQL (since SQL-99) added **roles** for better permission management.

#### Example:

```sql
CREATE ROLE teller;
GRANT teller TO Bob;
SET ROLE teller;
```

Roles:

- Represent **job functions** (e.g., "Teller", "Manager")
    
- Can be assigned to many users
    
- Easier to manage access (just revoke the role if someone leaves)

---

### 🔒 6. Multilevel Relational (MLR) Model

Based on **Bell-LaPadula (BLP)** for confidentiality.

Assigns **security labels** to:

- Relations (whole tables)
    
- Tuples (rows)
    
- Attributes (columns) ✅ Most common

#### Structure of MLR tuples:

Each tuple has:

- Values for attributes
    
- Classification level per attribute
    
- Tuple Classification (TC)

---

### 🔁 7. Polyinstantiation Problem

Happens when **same key exists with different data at different classification levels**.

#### Two Types:

1. **Invisible Polyinstantiation** (Low user inserts conflicting tuple):
    
    - DBMS lets it happen silently.
        
2. **Visible Polyinstantiation** (High user inserts conflicting tuple):
    
    - System keeps **both copies** of the same key.
        

#### Goal:

Prevent data leaks between clearance levels while keeping the system usable.

---

### 🔍 8. Practical Use of MLR

- **Low instance view**: What a **low-clearance user** sees (filtered).
    
- **High instance view**: What a **high-clearance user** sees (full data).
    
- Sensitive fields in low views are either **blank, NULL, or cover stories**.

---

## ✅ Key Takeaways for Exam:

|Concept|Key Point|
|---|---|
|**System R**|Uses DAC with privileges and delegation|
|**GRANT/REVOKE**|Manage user permissions; `WITH GRANT OPTION` enables delegation|
|**Views**|Enable content-based access control (filter by logic)|
|**SQL-99 RBAC**|Adds `ROLE` to simplify access control|
|**MLR Model**|Supports confidentiality via security labels|
|**Polyinstantiation**|Allows same key at different levels without conflict|
|**Low vs High Views**|Different data shown depending on user’s clearance|

---

## 📖 Pages with Examples for Reference:

- **Pages 5–9**: Delegation, GRANT/REVOKE, column-level permissions
    
- **Pages 17–21**: View-based filtering and protection
    
- **Pages 27–30**: Low/high view example for MLR
    
- **Pages 32–35**: Polyinstantiation (visible/invisible) examples