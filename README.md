# cybersecurityprofessional

Sr. Security engineer specializing in detection engineering, identity, and cloud security across Microsoft ecosystems, with a strong focus on developing toward cybersecurity architecture.

I design, deploy, and tune high-confidence detections in Microsoft Defender XDR, translating attacker behavior into actionable alerts, scalable controls, and automated response.

I am actively expanding into AI-driven security capabilities and governance to prepare organizations for the next generation of cloud and data protection challenges.

This repository highlights practical, production-style examples of custom detections, rule configuration, and operational implementation.

## Certifications

- CISSP – Certified Information Systems Security Professional  
- CCSP – Certified Cloud Security Professional
- SC-100 – Microsoft Certified: Cybersecurity Architect Expert       <https://learn.microsoft.com/api/credentials/share/en-us/87707645/74B66F2D3EF42E21?sharingId=8769A66020A07E4>
- AZ-500 – Microsoft Certified: Azure Security Engineer Associate    <https://learn.microsoft.com/api/credentials/share/en-us/87707645/7E1A9DD2D7A27E2A?sharingId=8769A66020A07E4>
- SC-300 – Microsoft Certified: Identity & Access Administrator      <https://learn.microsoft.com/api/credentials/share/en-us/87707645/CFC429D7C60CDA2C?sharingId=8769A66020A07E4>
- SC-400 – Microsoft Certified: Information Protection Administrator <https://learn.microsoft.com/api/credentials/share/en-us/87707645/A9522CAC1DA6CE58?sharingId=8769A66020A07E4>
- AI-900 - Microsoft Certified: Azure AI Fundamentals                <https://learn.microsoft.com/api/credentials/share/en-us/87707645/4F9813DD87B34313?sharingId=8769A66020A07E4>
- CompTIA SecurityX
- CompTIA CySA+  
- CompTIA Security+

Credly Profile for all certifications except Microsoft: <https://www.credly.com/users/dale-knight.19593117>  

---

## 🚧 In Progress – AI-102: Azure AI Engineer Associate  
### Exploring Secure AI Architecture & Prompt Governance

As organizations integrate Azure OpenAI and AI-driven copilots into enterprise environments, understanding how model behavior is shaped becomes critical. This lab demonstrates how system-level prompt configuration alone can materially influence model output, even when user input remains identical.

**Environment**
- Platform: Microsoft Foundry (Azure AI)
- Model: GPT-4o
- Deployment: Default configuration
- Variable changed: System prompt only

---

## 🎭 Prompt Conditioning Demonstration

### Test Scenario

**User Prompt (unchanged in both runs):**

> Explain prompt injection in simple terms and give 3 defensive controls an organization should implement.

Only the system-level instructions were modified.

---

### 🧪 Example 1 – Structured Scientific Tone (Doc Brown Conditioning)

**System Prompt Configuration**

![Doc Brown System Prompt](images/ai102/ai102-doc-brown-system-prompt.png)

**Model Output**

![Doc Brown Output](images/ai102/ai102-doc-brown-model-output.png)

---

### 🧪 Example 2 – Inverted Minimalist Tone (Yoda Conditioning)

**System Prompt Configuration**

![Yoda System Prompt](images/ai102/ai102-yoda-system-prompt.png)

**Model Output**

![Yoda Output](images/ai102/ai102-yoda-model-output.png)

---

## 🔎 Observation: Impact of Prompt Conditioning

Using identical user input, modifying only the system-level prompt resulted in significantly different tone, structure, and emphasis in the model’s response.

This demonstrates that LLM behavior can be materially influenced by upstream instructions, reinforcing the importance of:

- Prompt injection protections  
- Strict control over system prompt modification  
- Output validation and guardrails  
- Logging and monitoring AI configuration changes  

**In enterprise deployments, prompt configuration becomes part of the security boundary.**

---

## Detection Engineering Portfolio

Examples of custom detections I have designed and operationalized in Microsoft Defender XDR.

---

## VIP Display Name Impersonation – Sender Mismatch Detection

![Rule overview](images/RuleOverview.png)
![Frequency / severity](images/FrequencySeverity.png)
![Entity mapping](images/Entitymapping.png)


**Purpose:**  
Detects potential business email compromise (BEC) where a trusted executive or VIP display name is used but the message originates from an unauthorized sender.

### Detection Logic
Full query available here:  
[View full query](kql/vip-displayname-impersonation.kql)

**Rule Highlights**
- Runs hourly  
- High severity  
- Mailbox entity mapping  
- Supports automated remediation actions

---
---

## Inbound DMARC Domain Spoof – Auth Failure Correlation (Auto Soft Delete)

![Rule overview](images/dmarc-spoof-overview1.png)
![Rule overview](images/dmarc-spoof-frequency.png)
![Automated response](images/dmarc-spoof-automation.png)

**Purpose:**  
Detects inbound spoofing attempts targeting the organization’s domain by correlating SPF/DKIM/DMARC failures and Composite Authentication (CompAuth). Built for high-confidence detection and automated containment after tuning.

### Detection Logic
[View full query](kql/inbound-dmarc-domain-spoof.kql)

**Rule Highlights**
- Runs hourly (scheduled detection)
- High severity
- Mailbox entity mapping (recipient)
- Supports automated remediation (soft delete / hard delete / move to folder)

---

