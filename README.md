# cybersecurityprofessional
Security Engineering
## Certifications

- CISSP – Certified Information Systems Security Professional  
- CCSP – Certified Cloud Security Professional
- SC-100 – Cybersecurity Architect              <https://learn.microsoft.com/api/credentials/share/en-us/87707645/74B66F2D3EF42E21?sharingId=8769A66020A07E4>
- AZ-500 – Azure Security Engineer Associate    <https://learn.microsoft.com/api/credentials/share/en-us/87707645/7E1A9DD2D7A27E2A?sharingId=8769A66020A07E4>
- SC-300 – Identity & Access Administrator      <https://learn.microsoft.com/api/credentials/share/en-us/87707645/CFC429D7C60CDA2C?sharingId=8769A66020A07E4>
- SC-400 – Information Protection Administrator <https://learn.microsoft.com/api/credentials/share/en-us/87707645/A9522CAC1DA6CE58?sharingId=8769A66020A07E4>
- AI-900 - Azure AI Fundamentals                <https://learn.microsoft.com/api/credentials/share/en-us/87707645/4F9813DD87B34313?sharingId=8769A66020A07E4>
- CompTIA SecurityX
- CompTIA CySA+  
- CompTIA Security+

Credly Profile for all certifications except Microsoft: <https://www.credly.com/users/dale-knight.19593117>  


---

# Detection Engineering Portfolio

Examples of custom detections I have designed and operationalized in Microsoft Defender XDR.

---

## VIP Display Name Impersonation – Sender Mismatch Detection

![VIP impersonation detection example](images/vip-impersonation-example.png)

**Purpose:**  
Detects potential business email compromise (BEC) where a trusted executive or VIP display name is used but the message originates from an unauthorized sender.

### Detection Logic
Full query available here:  
👉 `kql/vip-displayname-impersonation.kql`

**Rule Highlights**
- Runs hourly  
- High severity  
- Mailbox entity mapping  
- Supports automated remediation actions

---

