
# 🔍 DVWA Vulnerability Assessment Report

**Author:** Jagadeesh Kommineni  
**Environment:** DVWA (Damn Vulnerable Web Application)  
**Platform:** Kali Linux  
**Tools Used:** Burp Suite, Apache2, MySQL, curl, DVWA, OWASP ZAP, Browser

---

## 📖 Project Overview

This project documents a complete penetration testing exercise on the **Damn Vulnerable Web Application (DVWA)**. The objective was to simulate real-world web application attacks in a controlled lab environment and understand how various vulnerabilities work, how they can be exploited, and most importantly, how they can be mitigated.

---

## 🔧 Setup Details

- **DVWA URL:** `http://localhost/dvwa`
- **Security Level:** Low (for full vulnerability exposure)
- **Web Server:** Apache2
- **Database:** MySQL
- **PHP Modules:** `php-gd`, `mysqli`, etc.
- **Configuration:** `config.inc.php` was manually set and MySQL credentials were verified.

---

## 🧪 Vulnerabilities Tested

| Vulnerability         | Status        | Risk Level | Tool Used       |
|-----------------------|---------------|------------|-----------------|
| Command Injection     | ✅ Exploited  | High       | Browser, curl   |
| SQL Injection         | ✅ Exploited  | Critical   | Burp Suite      |
| Stored XSS            | ✅ Exploited  | Medium     | Browser         |
| Reflected XSS         | ✅ Exploited  | Medium     | Browser         |
| File Upload (RCE)     | ✅ Exploited  | Critical   | shell.php       |
| CSRF                  | ⚠️ Attempted | Medium     | Custom HTML PoC |
| Brute Force Login     | ✅ Exploited  | High       | Burp Suite      |

---

## 📁 Folder Structure

```
DVWA_Report/
├── Environment/
│   ├── 01_login.png
│   ├── 02_dashboard.png
├── Command_Injection/
│   ├── 01_payload_input.png
│   ├── 02_command_output.png
├── SQL_Injection/
│   ├── 01_input.png
│   ├── 02_output.png
├── Stored_XSS/
│   ├── 01_submit_payload.png
│   ├── 02_alert_popup.png
├── File_Upload/
│   ├── 01_upload_shell.png
│   ├── 02_rce_output.png
├── CSRF/
│   ├── 01_html_poc.png
│   ├── 02_password_changed.png
├── Brute_Force/
│   ├── 01_intruder_setup.png
│   ├── 02_success_login.png
└── Summary_Report.docx
```

---

## 📋 OWASP Top 10 Mapping

This project also includes a compliance checklist against [OWASP Top 10 – 2021](https://owasp.org/Top10/) for educational alignment.

📄 [OWASP_Top10_Checklist_DVWA.docx](./OWASP_Top10_Checklist_DVWA.docx)

---

## 🛡️ Key Takeaways

- Importance of input validation and output encoding.
- Critical nature of default configurations and missing access controls.
- Risk of insecure file upload mechanisms.
- Real-world applicability of automated tools like Burp Suite & OWASP ZAP.

---

## 🧩 Recommendations

- Enable CSRF tokens and `SameSite` cookie policies.
- Implement account lockout, rate-limiting, and MFA.
- Sanitize and validate **all** inputs server-side.
- Apply security headers and deploy a WAF.

---

## 📚 Learning Outcome

This hands-on testing experience strengthened foundational knowledge of:
- Web attack vectors
- Common misconfigurations
- Security tools and payload crafting
- OWASP methodology for secure development


