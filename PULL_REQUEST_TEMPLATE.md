## 📋 Submission Information

**Name:** Enes Özkırdeniz
**Email:** ozkirdenizenes@gmail.com
**LinkedIn:** https://www.linkedin.com/in/enesozkirdeniz/
**Submission Date:** 2025/11/09

---

## ✅ Deliverables Checklist

Please confirm you've included all required items:

- [x] **Report** (PDF, max 5 pages)
  - [x] Section 1: Incident Analysis
  - [x] Section 2: Architecture Review
  - [x] Section 3: Response & Remediation
  
- [x] **Video Presentation** (10-15 minutes)
  - [ ] Link provided in `video_link.md`
  - [x] Video is accessible (tested in incognito)
  - [x] Duration is within guidelines

- [ ] **File Structure**
```
  submissions/firstname-lastname/
  ├── report.pdf
  ├── video_link.md
  └── notes.md (optional)
```

---

## 📊 Self-Assessment

**Time spent on this lab:** Approximately 12 hours

**Tools used:**
- Log analysis: Web Page
- Diagrams: Draw.io
- Video recording: QuicTime Player

**Confidence level:**
- [ ] Very confident in my analysis
- [x] Confident but some uncertainties
- [ ] Attempted my best with available knowledge

---

## 🎯 Brief Summary (2-3 sentences)

Investigated logs, network flows, and lab artefacts to reconstruct a multi-step intrusion originating from a single external IP that exploited a permissive “authorized test” window by referencing an internal schedule, lowering SOC triage sensitivity. Root causes were weak process controls around allow-listing, insufficient MFA/RBAC on sensitive paths, and monitoring gaps. I propose tokenized test windows, stricter ingress rules, MFA+RBAC, and a clarified detection playbook; evidence and the improved architecture are attached.


---

## 🔍 Key Findings Highlight

**Main attack vectors identified:**
1. Phishing: The email filter let the message in, even with a 'low reputation' warning. Because there was no MFA (no two-step login), the stolen password worked.
2. Broken Access Control: The Trading API did not check if the user_id and the account_id belonged to the same person. Because of this, 15+ other user portfolios returned 200 OK.
3. SQL Injection: The WAF (firewall) stopped basic attacks. But the attacker used a special 'inline comment' (hidden code), and this attack worked on the application.

**Most critical vulnerability:**
The lack of MFA (Multi-Factor Authentication).

**Top recommendation:**
This is the single most effective and highest-priority solution.

The entire attack chain analyzed in this report (Phishing -> Login -> SQL Injection -> Data Exfiltration) depended on the attacker successfully authenticating at 09:18:30.

If MFA (Multi-Factor Authentication) had been enabled, the stolen password alone would have been useless. The system would have challenged the attacker for a second factor (like a one-time code from the user's phone), which they did not have.

This single control would have stopped the entire attack chain before it even began. While other technical fixes (patching SQLi in the code, securing the API) are vital, enforcing MFA provides the fastest and broadest protection against all identity-based attacks.

---

## 💭 Challenges & Learnings

**What was most challenging?**
Identifying the social engineering component of the incident was the hardest part — the attacker used a legitimate-looking internal schedule to bypass trust boundaries, which required correlating technical logs with organizational context.

**What did you learn?**
I learned how critical it is to validate “authorized” sources and test windows with independent verification. Even small process gaps in access control or communication can open large attack surfaces.

**What would you do differently?**
Next time, I’d start with a clearer threat modeling step and ensure cross-team validation before trusting internal documents, plus automate log correlation for faster anomaly detection.

---

## 📝 Additional Notes _(optional)_

Any context, assumptions, or additional information you'd like evaluators to know:

[Write here]

---

## ⚖️ Declaration

I declare that:
- [x] This work is entirely my own
- [x] I have not copied from other submissions or answer keys
- [x] I have not modified the provided log files
- [x] All sources and tools are properly attributed
- [x] I understand plagiarism results in disqualification

**Signature:** Enes Özkırdeniz
**Date:** 2025/11/09

---

## 🚀 Ready for Review

By submitting this PR, I confirm that my work is complete and ready for evaluation.

---

_Thank you for your submission! Our team will review it within 1 week._
