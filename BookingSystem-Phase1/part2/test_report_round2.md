# 🧪 Test Report — Phase 1 / Part 2  
**Booking System – Updated Version**

**Tester(s):**   
- Abara Callistus

---

## 1️⃣ Introduction  

The purpose of this test was to **retest the updated Booking System application** and verify whether the previously reported vulnerabilities from Part 1 were fixed.  
The test included:

- Functional testing (registration form behavior)  
- Security testing (input validation, client-side checks)  
- Retesting the **Top 5 Immediate Actions** from Part 1  
- Running a full ZAP scan and comparing results with Round 1  

---

## 2️⃣ Test Environment  

| Component | Details |
|---------|---------|
| OS | Windows 11 |
| Browser | Chrome |
| Backend/Web App | Docker Compose (cybersec-phase1-part2) |
| URLs Tested | `http://localhost:8001/` (web), `http://localhost:8001/register` |
| Tools | OWASP ZAP 2.16.1 |

---

## 3️⃣ Scope of Testing  

### **Functional Tests Performed**
- Valid registration  
- Invalid email  
- Weak password  
- SQL injection attempts  
- XSS payload attempts  

### **Security Tests Performed**
- Cross-Site Scripting  
- SQL Injection  
- Missing field validation  
- Registration flow manipulation  
- OWASP ZAP automated scan  

---

## 4️⃣ Test Results Summary  

| Test Case | Expected Result | Actual Result | Status |
|----------|-----------------|---------------|--------|
| Invalid email input | Should show validation error | App blocked invalid email ✔ | **Passed** |
| Weak password (<8 chars) | Should be rejected | Error displayed ✔ | **Passed** |
| XSS payload in email | Should be rejected | Browser refused input ✔ | **Passed** |
| SQL injection in email | Should be rejected | Browser refused input ✔ | **Passed** |
| Successful registration | Should create user | Registered successfully ✔ | **Passed** |

---

## 5️⃣ Re-evaluation of Top 5 Issues from Part 1

### **1. Missing Input Validation — FIXED ✔**  
- Email field now enforces HTML5 validation.  
- SQL/XSS payloads are blocked **before submission**.

### **2. Weak Password Allowed — FIXED ✔**  
- Password must now be **at least 8 characters**.

### **3. No Date Validation — FIXED ✔**  
- Calendar picker prevents invalid birthday format.

### **4. Missing Role Validation — FIXED ✔**  
- Role now restricted to pre-defined dropdown values.

### **5. Application Accepted Malicious Inputs — FIXED ✔**  
- Client-side restrictions improved.  
- ZAP scan shows major reduction in alerts.

---

## 6️⃣ ZAP Scan Findings (Round 2 Results)

### **Total Alerts: 1**

| Alert | Risk Level | Instances |
|-------|-------------|------------|
| Absence of Anti-CSRF Tokens | Low | 1 |

### 🔍 **Summary**
In Round 1, ZAP found several alerts:  
- Missing CSP header  
- Missing clickjacking header  
- X-Content-Type-Options missing  
- No CSRF tokens  

In Round 2, **only 1 alert remains**, confirming improvements.

---

## 7️⃣ Detailed Findings – Round 2

### ⚠ **Absence of Anti-CSRF Tokens (Low)**  
- CSRF protection still not implemented.  
- This allows a possible Cross-Site Request Forgery risk.  
- Recommended fix:  
  - Add CSRF token to forms  
  - Validate token server-side  

---

## 8️⃣ Conclusion  

The updated application in Phase 1 / Part 2 shows **significant improvements**:

- All **input validation issues are fixed**  
- Registration workflow behaves correctly  
- ZAP scan results improved from **4 medium alerts → 1 low alert**  
- Security posture is improved but **CSRF protection still missing**

Overall, the system is **much more secure and stable** after the latest updates.

---

## 9️⃣ Attachments

- [`zap_report_round1.md`](../Part1/zap_report_round1.md)  
- [`zap_report_round2.md`](./zap_report_round2.md)

---

# ✅ End of Test Report (Phase 2)

