# TryHackMe — Defensive Security Intro: Cyber101

## Overview

This write-up documents my work on the Defensive Security Intro (Cyber101) room from TryHackMe.

The room introduces basic Security Operations Centre (SOC) concepts, including security monitoring, alert investigation, threat intelligence, and incident reporting.

---

## 1. An Attack Begins

The scenario starts inside FakeBank's SOC. The monitoring dashboard detected multiple failed login attempts against the organisation.

The alert was:

Suspicious Login Attempts

Severity:
`CRITICAL`

Description:
`Multiple failed login attempts detected`

The alert provided the following information:

| Field    | Value           |
| -------- | --------------- |
| Username | `dave.saunders` |
| Page     | `/login`        |
| Attacker | `ShadowFigures` |

The suspicious login activity resulted in the targeted account being locked.

### Flag

```text
THM{ACCOUNT-LOCKED}
```

---

## 2. Investigating the Attacker

The monitoring dashboard suggested that the attacker may be the `ShadowFigures` group.

The next step was to use FakeBank's threat intelligence system to record what had happened.

I searched for:

```text
ShadowFigures
```

I then updated the intelligence report with the information discovered from the previous alert.

### Incident Information

* Attacker: `ShadowFigures`
* Targeted Username: `dave.saunders`
* Targeted Page: `/login`

After submitting the information, the system displayed a successful update message.

### Flag

```text
THM{INTEL-UPDATED}
```

---

## 3. Incident Reports

The final step was to create an incident report documenting the attack.

The report required the username that had previously been locked and the page the attacker was attempting to access.

### Report Information

* Targeted Username: `dave.saunders`
* Targeted Page: `/login`

After submitting the report, FakeBank generated the following incident identifier:

```text
SEC-2026-341
```

### Incident Report Identifier

```text
SEC-2026-341
```

---

## Security Concepts Learned

### Security Monitoring

SOC monitoring dashboards collect and display security events from an organisation's environment. They help analysts identify activity that deviates from normal behaviour.

### Alert Investigation

Security alerts provide important context about an event, such as:

* The affected username
* The requested page
* The suspected attacker
* The severity of the event

### Threat Intelligence

Threat intelligence involves collecting, maintaining, and sharing information about threats and attackers.

Keeping threat intelligence updated helps security teams understand and respond to future incidents.

### Incident Reporting

Incident reports document what happened during a security event.

They provide a record that can be used for:

* Investigation
* Security training
* Improving defensive controls
* Future incident response
* Communicating with relevant authorities when necessary

---

## Flags and Results

| Task                       | Result                |
| -------------------------- | --------------------- |
| Suspicious Login           | `THM{ACCOUNT-LOCKED}` |
| Threat Intelligence Update | `THM{INTEL-UPDATED}`  |
| Incident Report ID         | `SEC-2026-341`        |

---

## Skills Practiced

* Security Operations Centre (SOC) fundamentals
* Security alert investigation
* Security monitoring dashboards
* Threat intelligence
* Incident response
* Incident reporting
* Identifying suspicious login activity
* Documenting security incidents

---

## Defensive Security Workflow

The exercise demonstrated a basic defensive security workflow:

```text
Detect → Investigate → Update Threat Intelligence → Report
```

The SOC first detected suspicious activity, then investigated the alert and identified the affected account and attacker. The information was added to the threat intelligence system, and finally the incident was documented in an incident report.

---

## Conclusion

This activity demonstrated how SOC analysts can use monitoring tools to detect suspicious activity, investigate security alerts, maintain threat intelligence, and document incidents.

The exercise provided practical experience with the basic workflow used when responding to a security incident.

---

## TryHackMe

Room: Defensive Security Intro — Cyber101

Platform: TryHackMe

Focus: SOC monitoring, threat intelligence, and incident reporting
