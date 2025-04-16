# Security Models: Practice Exam Questions 📝

## Multiple Choice Questions

### Question 1
Which security model is specifically designed to prevent information flow from higher security levels to lower security levels?

A. Biba Integrity Model  
B. Role-Based Access Control  
C. Bell-LaPadula Model  
D. Chinese Wall Model

**Answer: C. Bell-LaPadula Model**  
*Explanation: Bell-LaPadula focuses on confidentiality with its "No Read Up, No Write Down" rules that prevent information from flowing from higher to lower security levels.*

### Question 2
In which access control model would a user's previous access history determine what they can access in the future?

A. RBAC  
B. Chinese Wall  
C. ORCON  
D. Biba

**Answer: B. Chinese Wall**  
*Explanation: The Chinese Wall model uniquely bases access decisions on a user's access history - once they've accessed information from one company, they cannot access information from competing companies in the same conflict of interest class.*

### Question 3
A hospital implements a security model where doctors can only access records of patients under their care, except in emergencies when they can temporarily access any record with proper justification. This best describes which model?

A. Bell-LaPadula  
B. ORCON  
C. Clinical Information Systems Security (CISS)  
D. Role-Based Access Control

**Answer: C. Clinical Information Systems Security (CISS)**  
*Explanation: CISS is specifically designed for healthcare environments, featuring treatment relationships and emergency override ("break-glass") procedures.*

### Question 4
Which NIST RBAC level introduces the concept of role hierarchies?

A. Core RBAC  
B. Hierarchical RBAC  
C. Constrained RBAC  
D. Symmetric RBAC

**Answer: B. Hierarchical RBAC**  
*Explanation: Hierarchical RBAC extends Core RBAC by adding role hierarchies where senior roles inherit permissions from junior roles.*

### Question 5
The "No Read Down, No Write Up" principle is fundamental to which security model?

A. Bell-LaPadula  
B. Biba  
C. Chinese Wall  
D. ORCON

**Answer: B. Biba**  
*Explanation: The Biba Integrity Model enforces "No Read Down" (cannot read lower integrity data) and "No Write Up" (cannot write to higher integrity objects) to protect data integrity.*

## Short Answer Questions

### Question 6
Explain how the ORCON model differs from Discretionary Access Control (DAC).

**Answer:**  
While both ORCON and DAC give control to the information owner, they differ significantly. In DAC, once a user receives access to information, they can typically share it with others at their discretion. In ORCON, the original creator maintains persistent control - recipients cannot share the information with others without the originator's permission, even after they've received access. ORCON enforces the creator's control throughout the information lifecycle, whereas DAC transfers some control to each recipient.

### Question 7
A bank implements a security policy where loan officers cannot also be loan approvers for the same transaction. Which RBAC concept is being implemented?

**Answer:**  
This implements Separation of Duty (SoD), a key concept in Constrained RBAC. Specifically, this is Dynamic Separation of Duty, where a user may hold both roles but cannot activate them simultaneously for the same transaction. This prevents conflicts of interest and reduces fraud risk by requiring multiple people to complete sensitive transactions.

## Scenario-Based Questions

### Question 8
A government agency has implemented a security system with the following rules:
- Documents are classified as Confidential, Secret, or Top Secret
- Users have clearance levels matching these classifications
- Users can read documents at or below their clearance level
- Users can write documents at or above their clearance level

Which security model is being implemented? Explain why.

**Answer:**  
This scenario implements the Bell-LaPadula Model. The rules enforce "No Read Up" (users can only read at or below their clearance) and "No Write Down" (users can only write at or above their clearance). These rules prevent information from flowing from higher classification levels to lower ones, which is the primary goal of Bell-LaPadula - protecting confidentiality of classified information.

### Question 9
A consulting firm has implemented a security system where:
- Client data is organized by company
- Companies are grouped into industry sectors (banking, oil, retail, etc.)
- Once a consultant accesses Company A's data, they cannot access data from any competing company in the same industry sector
- Consultants can still access companies in different industry sectors

Identify the security model and explain how it addresses the firm's needs.

**Answer:**  
This implements the Chinese Wall Model. The companies represent Company Datasets (CDs), while industry sectors represent Conflict of Interest Classes (CoIs). The model prevents consultants from accessing information from competing companies, thereby preventing conflicts of interest while still allowing them to work with non-competing clients. This addresses the consulting firm's need to maintain client confidentiality and prevent information from being used to benefit competitors.

### Question 10
A hospital implemented RBAC with the following roles:
- Physician (can read/write medical records, order tests)
- Nurse (can read medical records, record vital signs)
- Billing Staff (can read/write billing information)
- Administrator (can read/write administrative records)

However, they found this didn't meet their needs because physicians needed different access based on which patients they were treating. What model would better address their requirements and why?

**Answer:**  
The Clinical Information Systems Security (CISS) Model would better address their requirements. While RBAC provides a good foundation by defining roles like Physician and Nurse, it doesn't account for the treatment relationship between providers and patients. CISS extends RBAC by adding the concept of patient-provider relationships, allowing physicians to access only their patients' records. It also provides context-based access for emergencies and supports team-based care. This better reflects healthcare workflows where access should be based not just on role but on treatment relationships.

## True/False Questions

### Question 11
In the Biba Integrity Model, a high-integrity subject can write to a low-integrity object.

**Answer: True**  
*Explanation: Biba's "No Write Up" rule prevents writing to higher integrity levels, but allows writing to lower integrity levels. This permits information to flow downward in terms of integrity.*

### Question 12
ORCON allows recipients of information to freely share it with others as long as they also have appropriate clearance.

**Answer: False**  
*Explanation: ORCON (Originator Controlled) specifically prevents recipients from sharing information without the originator's permission, regardless of the third party's clearance level.*

### Question 13
In RBAC, a user can be assigned to multiple roles simultaneously.

**Answer: True**  
*Explanation: RBAC allows users to be assigned to multiple roles based on their job functions. For example, someone might be both a "Department Manager" and a "Project Lead."*

### Question 14
The Chinese Wall model is primarily designed to protect data integrity.

**Answer: False**  
*Explanation: The Chinese Wall model is primarily designed to prevent conflicts of interest by creating "walls" between competing companies' data, not to protect data integrity.*

### Question 15
In the Bell-LaPadula model, a user with Secret clearance can write data to a Top Secret document.

**Answer: True**  
*Explanation: Bell-LaPadula's "No Write Down" rule allows writing to higher levels. A Secret-cleared user can write to Top Secret documents (writing up), but cannot read them (no read up).*

---

I hope these practice questions help you prepare for your exam! They cover the key concepts of each security model and test your understanding of their differences and applications.