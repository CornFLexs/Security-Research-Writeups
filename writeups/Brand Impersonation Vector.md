# 🛡️ Broken Social Link → Brand Impersonation Vector 🛡️  
**Category:** 🌐 Web Security | 🔗 Misconfiguration | ⚠️ Open Redirect / Impersonation Risk  
**Case Type:** Low Severity | Client-Side Issue

---

## 📝 1. Executive Summary
A misconfigured LinkedIn link was identified on the website. The link pointed to a non-existent profile, resulting in an error page. By creating a LinkedIn profile with the same username as referenced in the broken link, it was possible to redirect users to an attacker-controlled profile.

> **Key Insight:** The application linked to an unclaimed external resource, allowing takeover through username registration.

---

## 🎯 2. Target Overview
- **Application Type:** Public website  
- **Feature:** Social media links (LinkedIn, etc.)  
- **Entry Point:** LinkedIn redirect link  

---

## 🔍 3. Discovery Phase

### Observation
- Clicking the LinkedIn icon redirected to an error page  
- URL format:https://linkedin.com/company/example-name

- The profile did **not exist**

---

## ⚠️ 4. Vulnerability Details

### Root Cause
- Broken external link
- No validation of linked resource existence
- No ownership verification of social media profiles

### Vulnerability Type
**Unclaimed Resource / Social Link Takeover**

---

## 🚀 5. Exploitation

### Step 1: Identify Broken Link
```
https://linkedin.com/company/example-name
```

---

### Step 2: Verify Availability
- Checked if the username/profile was available on LinkedIn  
- Confirmed it was unclaimed  

---

### Step 3: Register Profile
- Created a LinkedIn profile/page using the same identifier:
```
example-name
```

---

### Step 4: Trigger Redirect
- Visiting the website’s LinkedIn link now redirects to attacker-controlled profile  

---

## 🐚 6. Impact

### Severity: Low → Medium (Context Dependent)

### Risks:
- Brand impersonation  
- User trust abuse  
- Phishing potential  
- Reputation damage  

### Realistic Impact:
- Users may assume the profile is official  
- Can be used to distribute malicious content or misinformation  

---

## 📊 7. Proof of Concept (PoC)

1. Visit website  
2. Click LinkedIn icon  
3. Observe broken link  
4. Register same username on LinkedIn  
5. Click link again  
6. Redirect now points to attacker-controlled profile  

---

## 🔐 8. Mitigation

- Regularly audit all external links  
- Ensure linked profiles are officially owned  
- Remove or update broken links  
- Use verified social media accounts  
- Optionally:
  - Monitor for brand impersonation  

---

## 🛠️ Tools Used
- Manual testing  
- Browser inspection  

---

## 🧠 Notes / Learnings
- Even simple misconfigurations can lead to impersonation risks  
- External links should be treated as part of attack surface  
- Unclaimed resources are a common oversight in production systems  
