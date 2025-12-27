# Network Defense Strategy 

This document outlines a proactive, multi-layered cybersecurity strategy based on the principle of **Defense-in-Depth**. This approach assumes that no single security control is infallible and therefore implements multiple layers of defense. If one layer fails, another is in place to detect or stop an attack.

---

## Layer 1: The Perimeter (The Outer Wall)

This layer secures the boundary between your private, internal network and the untrusted, public internet.

### Next-Generation Firewall (NGFW)
* **Function:** Acts as the primary gatekeeper, enforcing access control using stateful inspection, deep packet inspection, and application awareness.
* **Core Principle:** Configured with an **implicit deny** rule, where all traffic is blocked by default and only necessary business traffic is explicitly allowed.

### Demilitarized Zone (DMZ)
* **Function:** A buffer network for public-facing servers (e.g., web servers, email servers). It isolates these services from the internal network. If a public server is compromised, the attacker is contained within the DMZ, preventing direct access to internal resources.

---

## Layer 2: The Internal Network (Internal Guards)

This layer focuses on detecting and containing threats that have successfully bypassed the perimeter defenses.

### Intrusion Detection/Prevention System (IDS/IPS)
* **IDS (Detection):** A passive system that monitors traffic and sends an alert when a potential threat is detected.
* **IPS (Prevention):** An active system that sits in the traffic path and can block malicious activity in real-time.
* **Methods:** Utilizes both **signature-based** detection for known attacks and **anomaly-based** detection for new or unknown threats.

### Network Segmentation
* **Function:** Divides the internal network into smaller, isolated zones using technologies like VLANs. This strategy prevents **lateral movement**, containing a breach to a single segment. For example, a compromised device on a guest network cannot access critical servers on the finance network.

---

## Layer 3: The Endpoint (Securing the Final Target)

This layer secures the individual devices (laptops, servers, workstations) where data is stored and accessed.

### Endpoint Detection and Response (EDR)
* **Function:** Advanced antivirus that monitors endpoint behavior to detect suspicious activity (e.g., a Word document attempting to encrypt files), not just known malware files. Provides visibility and remote response capabilities.

### Host-Based Firewall
* **Function:** A software firewall running on each device, providing a final layer of protection if network-level controls fail.

### Patch Management
* **Function:** Ensures all operating systems and applications are regularly updated to fix known vulnerabilities that attackers frequently exploit.

---

## Layer 4: The People and Policies (The Human Layer)

This layer recognizes that technology alone is insufficient and focuses on user behavior and organizational policies.

### Principle of Least Privilege
* **Function:** Users and systems are granted only the minimum level of access and permissions necessary to perform their jobs. This limits the damage an attacker can do if they compromise an account.

### Multi-Factor Authentication (MFA)
* **Function:** Requires more than one form of verification to log in (e.g., password + mobile code), providing a powerful defense against stolen credentials.

### Security Awareness Training
* **Function:** Regular training for employees to help them recognize and report threats like phishing emails, turning them into a human firewall.
