# DISA-STIG-ID-WN10-AU-000500

---

## 🛠️ Manual Remediation Summary for DISA-STIG: WN10-AU-000500  
**Requirement**: *The Application event log size must be configured to 32,768 KB (32 MB) or greater.*  
**Tool Used**: Tenable (Nessus) Vulnerability Scanner  
**Platform**: Windows 10 Virtual Machine  

---

### 🔍 Objective:
Manually identify and remediate **DISA-STIG WN10-AU-000500**, which ensures that the **Application Event Log** is configured with sufficient size to support effective auditing and reduce the risk of overwritten events.

---

### ✅ Step-by-Step Process:

---

### **Step 1: Run Initial STIG Scan**  
- Performed a vulnerability scan on the Windows 10 VM using **Tenable** with the **Windows 10 STIG Audit Policy**.  
- Goal: Identify any misconfigurations related to DISA STIG compliance.  
- 📷 Screenshot: Initial scan launched and completed.
![inital Stig scan ](https://github.com/user-attachments/assets/8cd879ff-9752-457e-8045-8f8c3e79b84a)

---

### **Step 2: Review Scan Results and Select STIG to Remediate**  
- Selected **STIG ID WN10-AU-000500** based on the findings.  
- 📷 Screenshot: Scan findings showing the vulnerability related to insufficient event log size.
![inital stig scan findings](https://github.com/user-attachments/assets/cc473184-5dd2-484f-bf7a-05eb8f1b4868)

---

### **Step 3: Research and Plan Manual Remediation**  
- Identified that the **Event Log size** was set to **20,480 KB**, which is below the required **32,768 KB**.  
- Consulted the STIG check section and confirmed registry path requirements.  
- 📷 Screenshot: Registry check shows current value is non-compliant.
![STIG ID WN10-AU-000500](https://github.com/user-attachments/assets/3f8cfef2-fdc7-49f3-afde-9c97e202b285)

---
![The Application event log size must be configured to 32768 KB or greater](https://github.com/user-attachments/assets/58a6dce7-4a3d-4d62-8654-fd8102896e56)

---

### **Step 4: Investigate Registry Configuration**  
- Navigated to the registry key:  
  `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\EventLog\Application`  
- Found that the required **EventLog → Application** registry path did **not exist**.  
- 📷 Screenshot: Registry folder missing.

---
![REGISTRY NO FOLDERS](https://github.com/user-attachments/assets/09f41af6-e45c-4441-ab2b-1ee345716178)

---

### **Step 5: Manually Create Registry Keys and Apply Fix**  
- Manually created the missing registry folders:  
  - Created **EventLog** under `Windows`  
  - Created **Application** under `EventLog`  
- Set `MaxSize` (DWORD) to **32768** KB to meet compliance.  
- 📷 Screenshot: Registry path and value successfully created.
---
![registry path](https://github.com/user-attachments/assets/6112619a-834b-46a7-8378-045d17c99f31)

---

### **Step 6: Rescan to Validate Remediation**  
- Reran the STIG scan using Tenable to confirm that the manual fix resolved the issue.

  ---
  ![initial stig scan 2 ](https://github.com/user-attachments/assets/390db3f0-bd90-4bec-9aae-ea675b24cca1)
- 📷 Screenshot: STIG scan confirms successful remediation of WN10-AU-000500.
  ---

![initial stig scan 2 findings ](https://github.com/user-attachments/assets/8dadaa1f-a3af-40f2-af36-2730d5d601d4)


---

### **Step 7: Confirm Fix and Document**  
- The STIG finding for WN10-AU-000500 was cleared in the latest scan results.  
- This confirms the registry change successfully remediated the issue.  
- 📷 Screenshot: Final scan showing vulnerability resolved.
  ---
![initial stig scan 2 findings ](https://github.com/user-attachments/assets/b7d10377-c168-458c-ad4d-4963689bd65c)

---

## 🧪 SUMMARY 

In this lab, I manually remediated the DISA STIG vulnerability WN10-AU-000500, which requires the Application event log size to be configured to at least 32,768 KB. I began by scanning a Windows 10 virtual machine using Tenable with the Windows 10 STIG audit policy to identify vulnerabilities. From the scan results, I selected STIG ID WN10-AU-000500 to address. Upon inspection, I found that the required registry path (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\EventLog\Application) did not exist, and the current event log size was set below the required threshold. To remediate the issue, I manually created the missing registry folders and set the MaxSize DWORD value to 32768. After applying the fix, I rescanned the system using Tenable, which confirmed that the vulnerability had been resolved. 

## 🎯 Final Status:
✅ **DISA-STIG WN10-AU-000500 successfully remediated manually and verified through Tenable.**

---

# DISA-STIG-ID-WN10-AU-000500
