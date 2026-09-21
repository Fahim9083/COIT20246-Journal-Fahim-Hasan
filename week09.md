# Week 9 – Attacks and Vulnerabilities

## Task 1 – Knowledge Test

I completed the Week 9 Knowledge Test as part of the tutorial activities.

![Knowledge Test](images/09.png)

---

## Task 2 – CIA Protections

### Objective

To identify the important assets in my project network, especially data and equipment, and to use the CIA Triad (Confidentiality, Integrity, Availability) to decide what needs protecting and why.

### Project Scenario

The project network is a small business office. It has a local server that stores customer records and shared files, staff computers, a wireless network, a router/firewall with network switches, IP security cameras, and a backup system.

### Asset List

**Asset 1: Customer personal and financial records (stored on the server)**

- *Protection:* Confidentiality
  - *Reason:* Customers' names, contact details and payment information must not be visible to other customers or outsiders. A leak could cause identity theft and legal penalties under privacy laws.
- *Protection:* Integrity
  - *Reason:* Incorrect or altered records, such as changed bank details or invoice amounts, could cause financial loss and disputes.

**Asset 2: File and database server (equipment)**

- *Protection:* Availability
  - *Reason:* If the server is down, staff cannot access customer data or process orders, and the business stops operating.
- *Protection:* Integrity
  - *Reason:* If the server's software or configuration is tampered with, an attacker could hide malicious activity or corrupt every system that depends on it.

**Asset 3: Backups of business data**

- *Protection:* Availability
  - *Reason:* Backups are the recovery option after ransomware, hardware failure or accidental deletion. If they are unavailable, data loss may be permanent.
- *Protection:* Confidentiality
  - *Reason:* Backups hold a full copy of all data, so stealing a backup is as damaging as breaching the server.

**Asset 4: Router, firewall and network switches**

- *Protection:* Availability
  - *Reason:* If the core network devices fail, all internal systems and internet access are lost.
- *Protection:* Integrity
  - *Reason:* If an attacker changes firewall rules or routing settings, they could open a path into the network or redirect traffic without being noticed.

**Asset 5: Staff user accounts and passwords**

- *Protection:* Confidentiality
  - *Reason:* Stolen credentials let an attacker act as a legitimate user and bypass most other security controls.
- *Protection:* Integrity
  - *Reason:* Unauthorised changes to accounts or permissions could give an attacker administrator access.

**Asset 6: Wireless network (Wi-Fi) and its access key**

- *Protection:* Confidentiality
  - *Reason:* If the Wi-Fi key is shared with outsiders, they can connect to the internal network and capture traffic.
- *Protection:* Availability
  - *Reason:* Staff devices and wireless equipment rely on the Wi-Fi, so disruption stops work.

**Asset 7: Security cameras and their recordings**

- *Protection:* Availability
  - *Reason:* If the cameras are down, no footage will be available if a crime is committed.
- *Protection:* Integrity
  - *Reason:* Footage that has been edited or deleted cannot be trusted as evidence.
- *Protection:* Confidentiality
  - *Reason:* Recordings show staff and customers, so they must only be accessible to authorised people.

**Asset 8: Staff computers and laptops**

- *Protection:* Availability
  - *Reason:* Staff need working computers to do their jobs, and ransomware could lock them.
- *Protection:* Confidentiality
  - *Reason:* Lost or compromised devices may expose locally stored documents and saved logins.

### Summary of CIA Priorities

| Asset | Confidentiality | Integrity | Availability |
|---|:---:|:---:|:---:|
| Customer personal and financial records | ✔ | ✔ | |
| File and database server | | ✔ | ✔ |
| Backups | ✔ | | ✔ |
| Router, firewall and switches | | ✔ | ✔ |
| Staff accounts and passwords | ✔ | ✔ | |
| Wireless network and access key | ✔ | | ✔ |
| Security cameras and recordings | ✔ | ✔ | ✔ |
| Staff computers and laptops | ✔ | | ✔ |

---

## Task 3 – Threat Sources and Motivation

### Objective

To list the most likely types of adversarial threat sources (attackers) for the project network and the motivation of each.

### Threat Sources

| # | Threat Source | Motivation |
|---|---|---|
| 1 | Cybercriminals (for example, ransomware groups) | Financial gain by encrypting data and demanding payment, or by selling stolen customer and payment data. |
| 2 | Disgruntled or former employee (insider) | Revenge, or personal gain. They may already have legitimate access or know the network layout and weaknesses. |
| 3 | Competitor company | To gain a business advantage by stealing customer lists, pricing or other confidential information, or by disrupting operations. |
| 4 | Neighbour or nearby person | Wants free internet access and may try to guess or crack the Wi-Fi password. |
| 5 | Hacktivists | Ideological or political reasons, such as defacing a website or leaking data to embarrass the business. |
| 6 | Opportunistic attackers and automated bots | Curiosity, reputation among peers, or turning vulnerable devices into part of a botnet. These attackers scan the internet for easy targets rather than aiming at one organisation. |

### Discussion

**Insiders** and **cybercriminals** are the most likely and destructive sources for a small business. Because small enterprises frequently have poorer security, cybercriminals target them. Insiders can get beyond perimeter security because they already have authorised access. I have left out nation-state attackers because they are unlikely to target small businesses.
---

## Task 4 – Explore Vulnerabilities

### Objective

To examine real vulnerabilities published in the past 12 months and describe them using the standard CVE, CVSS and CWE information. I selected one Critical, one High and one Medium CVE.

### Summary

| Severity | CVE ID | CVSS v3 Score | Product | Vendor |
|---|---|:---:|---|---|
| Critical | CVE-2025-55182 | 10.0 | React Server Components | Meta |
| High | CVE-2025-59230 | 7.8 | Windows Remote Access Connection Manager | Microsoft |
| Medium | CVE-2025-55183 | 5.3 | React Server Components | Meta |

---

### CVE 1 – Critical: CVE-2025-55182 ("React2Shell")

| Item | Details |
|---|---|
| **CVE ID** | CVE-2025-55182 |
| **CVE Description** | A pre-authentication remote code execution vulnerability exists in React Server Components versions 19.0.0, 19.1.0, 19.1.1 and 19.2.0, including the packages `react-server-dom-parcel`, `react-server-dom-turbopack` and `react-server-dom-webpack`. The vulnerable code unsafely deserialises payloads from HTTP requests to Server Function endpoints. |
| **Date** | 3 December 2025 |
| **CVSS v3 Score** | 10.0 (Critical) – `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H` |
| **Confidentiality impact** | High |
| **Integrity impact** | High |
| **Availability impact** | High |
| **CWE** | CWE-502: Deserialization of Untrusted Data |
| **Company** | Meta (creator of React) |
| **Product affected** | React, a JavaScript library for building user interfaces. React Server Components allow part of a web application to run on the server instead of in the browser. The flaw also affects frameworks that use them, such as Next.js. |

**Simple explanation**

React Server Components use a unique format to transfer data from the browser to the server. Deserialisation is the process by which the server transforms this data back into objects without first adequately verifying it. As a result, an attacker can mislead the server into executing their own code by sending a single, well constructed web request. Any exposed server utilising the impacted versions could be completely taken over because no login is required. For this reason, the maximum score is 10.0.

**Detection and mitigation**

- Upgrade React and the affected packages to the patched versions. Later releases (19.0.4, 19.1.5 and 19.2.4) also fix follow-up issues.
- For Next.js and other frameworks, update to the vendor's patched release for the version in use.
- Identify applications that use React Server Components or Server Function endpoints, and list their dependencies.
- If patching is not immediately possible, disable Server Functions where possible and deploy web application firewall (WAF) rules.
- Monitor servers for unexpected commands or processes, because exploitation was observed shortly after disclosure and the flaw was added to CISA's Known Exploited Vulnerabilities catalogue.

---

### CVE 2 – High: CVE-2025-59230

| Item | Details |
|---|---|
| **CVE ID** | CVE-2025-59230 |
| **CVE Description** | Improper access control in Windows Remote Access Connection Manager allows an authorised attacker to elevate privileges locally. |
| **Date** | 14 October 2025 |
| **CVSS v3 Score** | 7.8 (High) – `CVSS:3.1/AV:L/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H` |
| **Confidentiality impact** | High |
| **Integrity impact** | High |
| **Availability impact** | High |
| **CWE** | CWE-284: Improper Access Control |
| **Company** | Microsoft |
| **Product affected** | Microsoft Windows (Windows 10, Windows 11 and Windows Server versions). The Remote Access Connection Manager (RasMan) service creates and manages dial-up and VPN connections. |

**Simple explanation**

Extremely high privileges are used by the RasMan service (SYSTEM). It improperly determines whether the person requesting the action is permitted to do so. This can be used by an attacker who already has a regular, low-privilege account on the computer to obtain SYSTEM rights and take over the entire system. Because the attacker must already be logged in locally in order to exploit it directly over the internet, it is graded High rather than Critical. It was added to CISA's Known Exploited Vulnerabilities collection when Microsoft revealed that it was being exploited prior to the release of a fix (a zero-day).

**Detection and mitigation**

- Install the October 2025 Microsoft security updates (or later) on all affected Windows systems.
- Use least privilege, so ordinary users do not have accounts with unnecessary access, which limits what an attacker can start with.
- Monitor for unexpected privilege escalation, such as standard user processes suddenly running as SYSTEM.
- Use endpoint protection and keep Windows Update enabled.

---

### CVE 3 – Medium: CVE-2025-55183

| Item | Details |
|---|---|
| **CVE ID** | CVE-2025-55183 |
| **CVE Description** | A source code exposure vulnerability in React Server Components. A crafted HTTP request to a vulnerable Server Function endpoint can cause the server to return the source code of Server Functions. |
| **Date** | 11 December 2025 |
| **CVSS v3 Score** | 5.3 (Medium) – `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:N/A:N` |
| **Confidentiality impact** | Low |
| **Integrity impact** | None |
| **Availability impact** | None |
| **CWE** | CWE-497: Exposure of Sensitive System Information to an Unauthorized Control Sphere |
| **Company** | Meta (creator of React) |
| **Product affected** | React Server Components, the React feature that runs parts of a web application on the server. |

**Simple explanation**

This flaw was found by researchers who were testing whether the fix for CVE-2025-55182 was complete. It does not let an attacker run code or crash the server. Instead, an attacker can trick a vulnerable server into revealing the source code of its server-side functions. The code itself is not customer data, but it can expose business logic and any secrets that developers hard-coded into it, such as API keys. That is why only confidentiality is affected, and only at a Low level.

**Detection and mitigation**

- Upgrade to the patched React versions (19.0.2, 19.1.3 and 19.2.2 or above). Later releases (19.0.4, 19.1.5 and 19.2.4) include further fixes.
- Update Next.js and other frameworks that bundle the vulnerable React packages.
- Never hard-code passwords or API keys in source code. Store them in environment variables or a secrets manager, so exposed code does not reveal them.
- Check whether the application uses React Server Components at all. If it does not, it is not affected.

---

### Reflection

The same product is the source of CVE-2025-55182 and CVE-2025-55183, the latter of which was discovered while researchers were evaluating the first's remedy. This demonstrates how one significant defect frequently results in further discoveries. The three CVEs also demonstrate why the type of defect is not the only factor influencing severity. The High one requires local access, the Medium one leaks data but does not grant system control, and the Critical one operates across the network and requires no login.
---

## Task 5 – Vulnerability Disclosures

### Viewpoint

Vulnerability disclosure strikes a balance between two risks: alerting people too soon, before a fix is available, and alerting them too late, when attackers might already be taking use of the vulnerability. I believe the best course of action is **coordinated (responsible) disclosure**. The vendor and the researcher agree on a timeline before the vulnerability is made public after the researcher exposes it to them in private.

**Why vendors take time.** A vendor needs to replicate the issue, identify the underlying cause, develop a solution, and test it on a variety of platforms and product versions. As demonstrated by the React CVEs, a hastily applied patch may cause other issues or leave the defect partially unresolved. Additionally, vendors may need to work with other businesses whose products rely on the same component and frequently release fixes on a set schedule, such as Microsoft's monthly Patch Tuesday.

**What is a reasonable time?** Software typically takes between 45 and 90 days. Because updates are more difficult to deploy, hardware or embedded devices can justify longer. I believe the timescale should be significantly shorter if a vulnerability is already being exploited in the wild since users need to know so they can take precautions.

**Should a researcher publish without permission?** If the vendor doesn't reply or doesn't take action, I believe a researcher may do so after a fair amount of time, but it shouldn't be the first option. Publication without a fix may provide attackers with a road map, endangering regular users. However, unrestricted secrecy eliminates any incentive for providers to address issues, and consumers are unable to protect themselves from risks they are unaware of. As long as the researcher first provides the vendor a genuine opportunity to reply and is prepared to extend the date when the vendor is obviously making progress, public deadlines are a reasonable way to hold suppliers accountable.

**The patch-gap problem.** Defenders benefit from disclosure, but attackers are also warned. Within days of the public publication, Microsoft's security team noticed attempts to exploit CVE-2025-55182. This demonstrates that organizations must promptly patch once a fix is made available to the public and that a vendor's advice should provide a clear explanation of how to mitigate the problem.

**Bug bounty programs and legal protection.** Researchers are encouraged to report vulnerabilities in private rather than selling or exposing them through bug reward programs and explicit vulnerability disclosure procedures. They function best when the vendor guaranties that researchers acting in good faith won't face legal repercussions. Without such safeguard, researchers might decide not to report at all.

**Conclusion.** My view is that coordinated disclosure with a firm but flexible deadline gives the best balance. It gives vendors time to produce a tested fix, gives users a fair chance to be protected, and still allows the researcher to go public if the vendor does not act.

---

## References

- React Team (2025). *Critical Security Vulnerability in React Server Components.* https://react.dev/blog/2025/12/03/critical-security-vulnerability-in-react-server-components
- React Team (2025). *Denial of Service and Source Code Exposure in React Server Components.* https://react.dev/blog/2025/12/11/denial-of-service-and-source-code-exposure-in-react-server-components
- GitHub Advisory Database. *CVE-2025-55182 (GHSA-fv66-9v8q-g76r).* https://github.com/advisories/GHSA-fv66-9v8q-g76r
- GitHub Advisory Database. *CVE-2025-55183 (GHSA-925w-6v3x-g4j4).* https://github.com/advisories/GHSA-925w-6v3x-g4j4
- Microsoft Security Blog (2025). *Defending against the CVE-2025-55182 (React2Shell) vulnerability.* https://www.microsoft.com/en-us/security/blog/2025/12/15/defending-against-the-cve-2025-55182-react2shell-vulnerability-in-react-server-components/
- Microsoft Security Response Center. *CVE-2025-59230.* https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59230
- NIST National Vulnerability Database. *CVE-2025-59230.* https://nvd.nist.gov/vuln/detail/CVE-2025-59230
- OWASP. *Vulnerability Disclosure Cheat Sheet.* https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet.html
- Microsoft. *Coordinated Vulnerability Disclosure.* https://www.microsoft.com/en-us/msrc/cvd
