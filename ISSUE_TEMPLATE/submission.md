---
name: Lab Submission
about: Submit your security incident lab analysis
title: '[SUBMISSION] Enes Özkırdeniz - Security Incident Lab'
labels: submission
assignees: ''
---

## 👤 Candidate Information

**Full Name:** Enes Özkırdeniz 

**Email:** ozkirdenizenes@gmail.com

**LinkedIn:** https://www.linkedin.com/in/enesozkirdeniz

**Location:** Izmir

**Submission Date:**  09/11/2025

---

## 📎 Submission Files

**Option A: Attached Files**
- Report PDF: [Attach here]
- Video link: https://www.youtube.com/watch?v=mT99EwQAVR8


---

## ⏱️ Time Tracking

**Total time spent:** 12 hours

**Breakdown:**
- Log analysis: 4 hours
- Architecture design: 2 hours
- Report writing: 4 hours
- Video creation: 2 hours

---

## 🎯 Summary

### Attack Vectors Identified
1. Web - SQL Injection (WAF Bypass)
2. Email - Phishing
3. API - Broken Object Level Authorization

### Key Findings
- Valid account reuse after phishing; MFA not enforced.
- WAF running with basic rules, OWASP CRS not in Block; rate limits missing on /portfolio/ and export endpoints.

### Top 3 Recommendations
1. Enforce MFA for all users; revoke sessions and force org-wide password resets.
2. Fix auth & injection: add object-level checks in Trading API; replace dynamic SQL with parameterized queries; deploy custom WAF rule for inline comments and enable OWASP CRS (Block).
3. WAF bypass with MySQL inline comments (e.g., /*!50000...*/) at 09:23; dynamic SQL enabled execution → CSV export ~892 KB.

---

## 🛠️ Tools Used

**Analysis:**
- Web Browser
- VS Code

**Diagrams:**
- Draw.io

**Video:**
- 

**Other:**
- 

---

## ✅ Checklist

Please confirm:

- [x] Report is max 5 pages
- [ ] Video is 10-15 minutes
- [x] All log files were analyzed
- [x] Timeline is timezone-corrected
- [x] Framework mappings included (ISO 27001, NIST, OWASP)
- [ ] Architecture diagram included
- [ ] Video link is tested and working
- [x] No plagiarism / proper attribution
- [x] Original work, not AI-generated

---

## 💬 Optional Feedback

**What did you think of this lab?**

- Very useful and realistic. The scenario ties phishing, IDOR, and SQLi together, so I could see the full kill chain. The tasks are clear and the evidence-driven approach helped me learn faster.


**Any suggestions for improvement?**


**Would you recommend this to others?**
- [x] Yes
- [ ] No
- [ ] Maybe

---

## 📧 Contact Preference

**Preferred contact method:**
- [x] Email
- [x] LinkedIn
- [ ] GitHub

**Best time to reach you:**


---

## ⚖️ Declaration

I declare that this submission is my original work and I have followed all guidelines.

**Name:** Enes Özkırdeniz  
**Date:** 09/11/2025

---

_Thank you for your submission! We'll review it and get back to you within 1 week._
