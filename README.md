## How to Delete or Clear Remote Desktop Connection (RDP) IP Address History in Windows


## 🎯 Purpose

This manual provides clear, standardized instructions for Information Technology (IT) teams to remove Remote Desktop Connection (RDP) IP address history and saved credentials from Windows systems. This procedure is commonly used for **security hardening**, **privacy protection**, and **troubleshooting**.

---

## 👥 Intended Audience

* IT Support Engineers
* System Administrators
* Desktop Support Teams

---

## 🧩 Scope

This document applies to Microsoft Windows endpoints where Remote Desktop Connection (RDP) has been used previously.

---

## 💻 Operating System Compatibility

* **Windows 11**
* **Windows 10**

> ✅ These steps work for both Windows 10 and Windows 11.

---

## 🗂️ Overview

Remote Desktop Connection stores connection history (IP addresses or hostnames) and credentials in the **Windows Registry** and **Credential Manager**. Clearing this information ensures that previously accessed systems are no longer visible or auto-filled.

---

## 🛠️ Procedure

### 1️⃣ Clear RDP History from the Windows Registry (Primary Method)

Remote Desktop stores IP address and hostname history in multiple registry locations.

---

### 🔹 Step A: Clear “MRU” (Most Recently Used) Entries

1. Press **Win + R** to open the Run dialog.
2. Type **regedit** and press **Enter**.
3. Navigate to the following registry path:

```
HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Default
```

4. On the right-hand pane, locate and **delete entries similar to the following**:

```
MRU0 192.168.1.110
MRU1 192.168.1.111
MRU2 192.168.1.123
...
```

📝 These entries represent previously connected IP addresses or hostnames.

---

### 🔹 Step B: Clear RDP History from the “Servers” List

While still in **Registry Editor**, navigate to:

```
HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Servers
```

📁 Each subfolder represents an IP address or hostname that the user has previously connected to.

5. **Delete the folder for a specific IP address** you want to remove
   **— OR —**
6. Delete the entire **Servers** folder to remove **all saved RDP connection history**.

---

## 🔐 2️⃣ Delete Saved RDP Credentials

If login credentials were saved during previous RDP sessions, they must be removed separately.

1. Press **Win + R**.
2. Type **control keymgr.dll** and press **Enter**.
3. Select **Windows Credentials**.
4. Look for credential entries formatted as:

```
TERMSRV/<IP address>
```

5. Select the relevant entry and click **Remove**.

---

## ⚠️ Notes and Best Practices

* Editing the Windows Registry can affect system behavior; proceed with caution.
* Always **back up the registry** before making changes.
* Ensure you have the appropriate **user permissions**.
* These actions only affect the **current user profile**.

---

## 📌 Summary

By completing the steps in this document, IT staff can successfully:

* Remove stored RDP IP address history
* Clear saved hostnames from the Remote Desktop client
* Delete stored RDP credentials

This helps maintain system security, user privacy, and clean RDP configurations.

---
