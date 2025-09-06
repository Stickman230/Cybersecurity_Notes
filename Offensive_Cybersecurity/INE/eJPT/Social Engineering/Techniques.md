#eJPT #INE #SocialEngineering #Phishing #SpearPhishing #Pretexting


| TOOL      | Purpose                      |
| --------- | ---------------------------- |
| *Gophish* | Social Engineering Framework |
|           |                              |

# Techniques

## Phishing

1. **Planning & Reconnaissance**: Attackers research the target organization to identify potential targets, gather information about employees, and understand the organization's communication channels and protocols.

2. **Message Crafting:** Attackers create deceptive emails or messages designed to mimic legitimate communications from trusted sources, such as colleagues, IT departments, or financial institutions. These messages often include urgent or compelling language to evoke a sense of urgency or fear.

3. **Delivery**: Attackers send phishing emails or messages to targeted individuals within the organization, using techniques to bypass spam filters and security controls. They may also leverage social engineering tactics to increase the likelihood of recipients opening the messages.

4. **Deception & Manipulation:** The phishing messages contain malicious links, attachments, or requests for sensitive information. Recipients are deceived into clicking on links, downloading attachments, or providing login credentials under false pretenses. 

5. **Exploitation**: Once the victim interacts with the phishing message, attackers exploit vulnerabilities in the target's systems or applications to gain unauthorized access, install malware, or steal sensitive information.

### Using GoPhish

*GoPhish is an open-source phishing framework designed for penetration testers and security professionals to simulate phishing attacks against their own organizations*

- The platform provides a built-in email template editor with a WYSIWYG (What You See Is What You Get) interface,
- GoPhish enables users to create phishing landing pages that mimic legitimate login portals or websites. These landing pages can be customized to capture credentials, personal information, or other sensitive data from targets.
- This tool supports campaign scheduling and automation, allowing users to schedule campaign launches at specific dates and times or set up recurring campaigns

---

## Spear Fishing

**Target Selection & Research:** Attackers carefully select their targets based on specific criteria, such as job roles, departments, or organizational hierarchies.
● Extensive reconnaissance is conducted to gather information about the targets, including names, job titles, roles, responsibilities, work relationships, and personal interests.
● Publicly available sources, social media profiles, corporate directories, and leaked data may be mined to compile detailed profiles of the targets.


2. **Message Tailoring:** Using the gathered information, attackers craft highly personalized and convincing emails or messages designed to appear legitimate and trustworthy.
● The content of the messages may reference recent events, projects, or activities relevant to the target's role or interests to enhance credibility.
● Attackers may impersonate trusted individuals, such as colleagues, supervisors, or external partners, to increase the likelihood of the targets opening the messages and taking the desired actions.


3. **Delivery:** Spear phishing messages are delivered to the targeted individuals via email, social media, instant messaging platforms, or other communication channels.
● Attackers employ tactics to bypass email security filters and anti-phishing mechanisms, such as using compromised or spoofed email accounts, exploiting zero-day vulnerabilities, or leveraging trusted third-party services.

---

## Pretexting

*Pretexting is the process of creating a false pretext or scenario to gain the trust of targets and extract sensitive information. This may involve impersonating authority figures, colleagues, or service providers to manipulate victims into divulging confidential data.*

- Unlike other forms of social engineering that rely on deception or coercion, pretexting involves the creation of a false narrative or context to establish credibility and gain the trust of the target.

#### Characteristics 

- **False Pretense:** The attacker creates a fictional story or pretext to deceive the target into believing that the interaction is legitimate and trustworthy. This pretext often involves impersonating someone with authority, expertise, or a legitimate reason for requesting information or assistance.

- **Establishing Trust:** The attacker uses the pretext to establish rapport and build trust with the target. This may involve leveraging social engineering techniques, such as mirroring the target's language, tone, and behavior, to create a sense of familiarity and connection.

- **Manipulating Emotions:** Pretexting often exploits human emotions, such as curiosity, fear, urgency, or sympathy, to manipulate the target's behavior. By appealing to these emotions, the attacker can influence the target's decision-making process and increase compliance with their requests.

- **Information Gathering:** Once trust is established, the attacker seeks to extract sensitive information or access privileges from the target. This may involve posing as a trusted entity (e.g., colleague, vendor, service provider) and requesting information under the pretext of a legitimate need or emergency.

- **Maintaining Consistency:** To maintain the illusion of legitimacy, the attacker ensures that the pretext remains consistent and plausible throughout the interaction. This may require careful planning, research, and improvisation to adapt to the target's responses and maintain credibility.

#### Example

- **Tech Support Scam**: An attacker poses as a technical support representative from a legitimate company and contacts individuals, claiming that their computer is infected with malware. = *Remote Access*

- **Job Interview Scam:** An attacker pretends to be a recruiter or hiring manager from a reputable company and contacts job seekers, offering them fake job opportunities or conducting fraudulent job interviews.  = *Confidential/Payment data*

- **Emergency Situation:** An attacker fabricates an emergency situation, such as a security breach, data leak, or system outage, and contacts employees, requesting immediate assistance or information. = *Remote Access*