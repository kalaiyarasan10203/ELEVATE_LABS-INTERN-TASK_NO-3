# ELEVATE_LABS-INTERN-TASK_NO-3
# Nessus Vulnerability Mitigation Report

## 📅 Date: 31 May 2025
## 🔍 Scan Type: Basic Network Scan
## 🛡️ Tool Used: Tenable Nessus Essentials

---

## 🔴 High Risk Vulnerability

### 🔐 Vulnerability: OpenJDK <= 8u442 / 11.0.26 / 17.0.14 / 21.0.6 / 24.0.0 Multiple Vulnerabilities  
**CVE IDs:** CVE-2025-21587, CVE-2025-30691, CVE-2025-30698  
**Severity:** High  
**Affected Host:** 192.168.110.165  
**Path:** `/usr/lib/jvm/java-17-openjdk-amd64/`  
**Installed Version:** 17.0.14  
**Fixed Version:** > 17.0.14

### 🔎 Description:
Multiple remotely exploitable vulnerabilities exist in Oracle Java SE and GraalVM components (JSSE, Compiler, 2D). These vulnerabilities may allow unauthorized access to critical data, and unauthorized code execution when loading untrusted code such as Java Web Start apps or applets.

### 🛠️ Mitigation:
- **Upgrade OpenJDK** to a version **newer than 17.0.14**.
- Apply the latest security patches from the [OpenJDK advisory](https://openjdk.java.net/groups/vulnerability/advisories/2025-04-15).
- Remove or sandbox any untrusted Java applets or code running in the environment.

---

## 🟠 Medium Risk Vulnerability

### 🔐 Vulnerability: OpenSSL < 3.1.7 - Buffer Overread on SSL_select_next_proto  
**CVE ID:** CVE-2024-5535  
**Severity:** Medium  
**Affected Host:** 192.168.110.165  
**Path:** `/usr/lib/x86_64-linux-gnu/ruby/3.1.0/openssl.so`  
**Reported Version:** 3.1.5  
**Fixed Version:** 3.1.7

### 🔎 Description:
Calling `SSL_select_next_proto` with an empty client protocols buffer may lead to a buffer overread. This can result in leaking up to 255 bytes of memory, possibly revealing sensitive data.

### 🛠️ Mitigation:
- Upgrade OpenSSL to **version 3.1.7 or later**.
- Ensure applications calling OpenSSL APIs properly validate protocol lists before use.
- Validate all server/client ALPN or NPN configurations to avoid empty protocol lists.

---

## 🧩 Notes:
- These vulnerabilities were detected using Nessus Essentials and rely on version checks.
- Apply mitigations promptly to prevent potential exploitation.
- Always test updates in a staging environment before deploying to production systems.

---

## ✍️ Report Prepared by:
**Kalaiyarasan K.**  
Student | Ethical Hacking Enthusiast  
[LinkedIn](https://www.linkedin.com/in/k-kalaiyarasan-17833a308)

