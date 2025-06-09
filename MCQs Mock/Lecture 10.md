## ✅ GJU-Style MCQs – Lecture 10: **Database Security**

---

### **1. Which of the following is NOT a privilege supported by the System R authorization model?**

A) SELECT  
B) DROP  
C) GRANT  
D) UPDATE

> **Answer:** C) GRANT  
> _Explanation:_ GRANT is a **command**, not a privilege.

---

### **2. What does the `WITH GRANT OPTION` in SQL allow a user to do?**

A) Use a privilege once only  
B) Revoke the same privilege from others  
C) Grant a privilege they were given to another user  
D) Create new privileges

> **Answer:** C) Grant a privilege they were given to another user

---

### **3. In System R, when a privilege is revoked and all subsequent privileges granted by the receiver are also removed, this is known as:**

A) View-based revocation  
B) Cascading revoke  
C) Recursive inheritance  
D) Multi-user revocation

> **Answer:** B) Cascading revoke

---

### **4. Which SQL object is used to enforce content-based access control by filtering visible data?**

A) Stored procedure  
B) Trigger  
C) View  
D) Role

> **Answer:** C) View

---

### **5. What is the main purpose of content-based access control using views?**

A) Prevent table creation  
B) Block unauthorized SQL syntax  
C) Restrict access to specific rows or columns  
D) Enforce encryption at rest

> **Answer:** C) Restrict access to specific rows or columns

---

### **6. Which SQL command combination is the safest method to grant table access in a secure database system?**

A) GRANT SELECT ON table TO user  
B) GRANT ALL PRIVILEGES TO user  
C) CREATE VIEW + GRANT SELECT ON view TO user  
D) GRANT EXECUTE ON PROCEDURE TO user

> **Answer:** C) CREATE VIEW + GRANT SELECT ON view TO user

---

### **7. The SQL-99 standard introduced what major improvement to the System R model?**

A) Scripting triggers  
B) Role-Based Access Control  
C) Transparent encryption  
D) Cross-table joins

> **Answer:** B) Role-Based Access Control

---

### **8. What happens if a view definer loses SELECT access to the base table?**

A) The view continues to work normally  
B) The system reassigns access dynamically  
C) The view is dropped or becomes invalid  
D) The view becomes read-only

> **Answer:** C) The view is dropped or becomes invalid

---

### **9. In the Multilevel Relational (MLR) model, which of the following is TRUE?**

A) Classification is assigned only to entire databases  
B) All tuples must have the same security level  
C) Each attribute and row may have its own classification  
D) Labels are stored only in system catalogs

> **Answer:** C) Each attribute and row may have its own classification

---

### **10. What security property does polyinstantiation help enforce in a multilevel secure database?**

A) Integrity  
B) Authentication  
C) Availability  
D) Confidentiality

> **Answer:** D) Confidentiality  
> _Explanation:_ Polyinstantiation avoids leaking information by allowing multiple rows with the same primary key at different security levels.

---

### **11. What is a “low instance view” in the MLR model?**

A) View with corrupted or NULL values  
B) View showing all classifications  
C) View limited to data the user is cleared to see  
D) View that maps high data to encrypted values

> **Answer:** C) View limited to data the user is cleared to see

---

### **12. In polyinstantiation, which of the following scenarios best describes the “visible” type?**

A) High-level user inserts a duplicate key and the system hides it  
B) Low-level user inserts a tuple, silently overwriting a high-level one  
C) System allows two tuples with the same key at different levels, both visible to the high-level user  
D) System rejects duplicate entries based on key constraints

> **Answer:** C) System allows two tuples with the same key at different levels, both visible to the high-level user

---

### **13. What is the main security benefit of using views in database access control?**

A) Faster query optimization  
B) Storage reduction  
C) Fine-grained access filtering  
D) Backup management

> **Answer:** C) Fine-grained access filtering

---

### **14. Which of the following is a disadvantage of using views for security?**

A) Too flexible for enterprise needs  
B) Lack of support in SQL standards  
C) View validity depends on the base table access of the definer  
D) Views can’t be combined with roles

> **Answer:** C) View validity depends on the base table access of the definer

---

### **15. In SQL-99, what does the `SET ROLE` command do?**

A) Grants admin privileges  
B) Enables a specific user-defined function  
C) Activates a particular role during a session  
D) Resets user access levels

> **Answer:** C) Activates a particular role during a session