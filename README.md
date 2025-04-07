# 🛡️ Threat Hunt Project: VM Internet Exposure

## 📌 Objective

Identify misconfigured virtual machines in a shared services cluster that were unintentionally exposed to the public internet. Investigate for any brute-force login attempts and determine if unauthorized access occurred.

---

## 🔍 Hunt Process Overview

### 1. Preparation
- **Goal**: Define scope of the threat hunt.
- **Hypothesis**: Older VMs without account lockout settings may have been exposed to brute-force login attacks.

### 2. Data Collection
- Focused on:
  - `DeviceInfo`
  - `DeviceLogonEvents`

### 3. Data Analysis
- Investigated:
  - High volume of failed logins
  - Correlation between failed and successful attempts

### 4. Investigation
- Mapped findings to MITRE ATT&CK framework
- Analyzed timelines and actor behavior

### 5. Response
- NSGs were hardened
- MFA and lockout policies implemented

### 6. Documentation
- Findings saved in `/findings/`
- Queries used are in `/queries/`
- MITRE and Response documentation available

### 7. Improvement
- Identified lack of lockout policy and monitoring as improvement areas.

---

## 📂 Project Structure

| Folder | Description |
|--------|-------------|
| [queries/](queries) | KQL scripts used during the hunt |
| [findings/](findings) | Timeline and conclusions |
| [documentation/](documentation) | Response actions and TTP mapping |


---

## 🔐 Key MITRE ATT&CK TTPs

- **T1595** - Active Scanning  
- **T1110** - Brute Force  
- **T1078** - Valid Accounts  
- **T1589** - Identity Gathering  

---

## ✅ Summary

- No brute force successes detected.
- All logons came from the known `labuser` account.
- Mitigation steps applied to prevent future exposures.
