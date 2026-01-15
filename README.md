# FUTURE_CS_01 
My first task as part of my virtual internship with Future Interns in the field of Cybersecurity. 

# 🔐 Basic Website Security Assessment (Passive Audit)

This repository contains a **passive, ethical security assessment report** conducted on a public website as part of a **security consulting learning exercise**.

The goal of this assessment is not to hack, but to identify common, publicly observable security gaps and explain them in a business-friendly manner.

---

## 🌐 Target Website

- **Website:** Wikipedia  
- **URL:** https://www.wikipedia.org  
- **Assessment Type:** Passive / Read-only Security Review  
- **Scope:** Public-facing pages only  

---

## ⚖️ Ethics & Scope Disclaimer

✔ Publicly accessible pages only  
✔ No authentication bypass  
✔ No exploitation or active attacks  
✔ No service disruption  

> This assessment follows responsible security auditing practices and does **not** attempt to compromise the target website.

---

## 🛠️ Tools Used

| Tool | Purpose |
|----|----|
| Browser Developer Tools | Inspect HTTP headers, cookies |
| OWASP ZAP (Passive Mode) | Detect configuration weaknesses |
| Manual Review | Policy and disclosure visibility |

---

## 📊 Key Findings

### 🟡 Finding 1: Inconsistent Security Headers  
**Risk Level:** Medium  
**Tool Used:** Browser DevTools, OWASP ZAP (Passive)

**Issue**  
Some standard HTTP security headers, such as `X-Frame-Options` and `X-Content-Type-Options`, are not consistently visible across all public pages.

**Why It Matters**  
Security headers instruct browsers to block unsafe behaviours. Missing or inconsistent headers may increase exposure to:
- Clickjacking
- MIME-type sniffing attacks

**Business Impact**  
Users may be exposed to manipulated or embedded content, which can affect trust and brand reputation.

**Recommended Remediation**  
- Enforce consistent security headers at the CDN or web server level  
- Apply a standardised security header policy across all public pages  

---

### 🟢 Finding 2: Cookies Not Uniformly Scoped  
**Risk Level:** Low  
**Tool Used:** Browser DevTools (Application → Cookies)

**Issue**  
While most cookies use secure attributes, not all cookies consistently apply the `SameSite` attribute.

**Why It Matters**  
Improper cookie scoping may increase exposure to cross-site request forgery (CSRF) risks.

**Business Impact**  
Low likelihood of direct impact, but could affect authenticated users in certain edge cases.

**Recommended Remediation**  
- Apply `Secure`, `HttpOnly`, and appropriate `SameSite` attributes consistently  
- Review cookie configurations after feature updates  

---

### 🟢 Finding 3: No Prominent Security Disclosure Link  
**Risk Level:** Low  
**Tool Used:** Manual Review

**Issue**  
A clear security disclosure or vulnerability reporting link is not prominently visible on the landing page.

**Why It Matters**  
Security researchers may not know how to responsibly report vulnerabilities.

**Business Impact**  
Delayed reporting of issues could increase the exposure window for potential risks.

**Recommended Remediation**  
- Add a visible “Security” or “Report a Vulnerability” link  
- Encourage responsible disclosure practices  

---

## 📌 Summary

- Overall security posture is **strong**
- No critical vulnerabilities identified
- Improvements mainly relate to **security best practices and governance**

This assessment demonstrates how **passive security reviews** help organisations understand and prioritise risks without disrupting services.

---

## 📚 Purpose of This Repository

- Learn ethical security auditing  
- Practice professional vulnerability reporting  
- Demonstrate a security consulting mindset  

---

## 🧠 Author

**Role:** Security Analyst (Training Exercise)  
**Focus:** Web Security, Risk Assessment, Ethical Auditing

---

> ⚠️ This repository is for **educational purposes only** and does not represent an official audit of Wikipedia.

