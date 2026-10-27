# Introduction to SOAR

## Overview

This room explores Security Orchestration, Automation, and Response (SOAR) and explains how it helps Security Operations Center (SOC) teams improve their incident response processes.

It covers traditional SOC challenges, SOAR capabilities, security playbooks, and a practical threat intelligence workflow.

## Learning Objectives

- Understand traditional SOC operations and their challenges.
- Learn how SOAR improves security operations.
- Understand orchestration, automation, and response.
- Explore security playbooks for phishing and CVE patching.
- Configure a threat intelligence workflow.

## Key Concepts

### Traditional SOC Challenges

Traditional SOC teams face several challenges:

- Alert fatigue caused by large volumes of security alerts.
- Disconnected security tools that require manual switching.
- Manual investigation and response procedures.
- Shortages of qualified cybersecurity professionals.

### What Is SOAR?

Security Orchestration, Automation, and Response (SOAR) integrates security tools into a unified platform, allowing SOC analysts to coordinate investigations, automate repetitive tasks, and manage incidents more efficiently.

The three main capabilities are:

- Orchestration: Integrates security tools and coordinates their workflows.
- Automation: Executes predefined actions without requiring manual intervention at every step.
- Response: Performs actions such as blocking malicious IP addresses, disabling compromised accounts, and creating incident tickets.

SOAR reduces repetitive work but does not replace SOC analysts. Human analysis remains essential for complex investigations and critical decisions.

### SOAR Playbooks

A playbook is a predefined workflow that specifies the actions to take when handling a particular security incident.

#### Phishing Playbook

A phishing playbook can automate the investigation of suspicious emails by checking URLs, analyzing attachments, consulting threat intelligence sources, creating tickets, and initiating remediation.

#### CVE Patching Playbook

A CVE patching playbook helps security teams manage newly disclosed vulnerabilities. It can retrieve vulnerability information from advisory lists, assess risk, create patching tickets, deploy patches, and verify whether assets remain vulnerable.

If vulnerabilities persist after patch deployment, the SOC may need to develop a mitigation plan.

## Practical Workflow

The practical exercise focuses on integrating threat intelligence into a SOAR workflow.

The workflow involves deciding which actions should be automated and which require manual analysis. Automated actions may include collecting threat intelligence, extracting indicators, checking reputation, and updating incident tickets. Manual intervention remains important when investigating unfamiliar threats or approving sensitive response actions.

## Questions and Answers

### Task 2: Traditional SOC and Challenges

Question: How would you describe the experience of an overload of security events being triggered within a SOC?

Answer: Alert Fatigue

### Task 3: Overcoming SOC Challenges with SOAR

Question: The act of connecting and integrating security tools and systems into seamless workflows is known as?

Answer: Orchestration

Question: What do we call a predefined list of actions to handle an incident?

Answer: Playbook

### Task 4: Building SOAR Playbooks

Question: Is manual analysis vital within a SOAR workflow?

Answer: Yay

Question: From where is the CVE Patching playbook fetching the new CVEs?

Answer: Advisory lists

Question: If assets are still vulnerable after the patch is deployed, what does the SOC develop next?

Answer: Mitigation Plan

### Task 5: Threat Intel Workflow Practical

Question: What is the flag received?

Answer: Obtain and verify the flag by running the configured workflow in the TryHackMe lab.

## Conclusion

SOAR improves SOC efficiency by integrating security tools, automating repetitive tasks, and standardizing incident response through playbooks. Although automation reduces the workload on security teams, analysts remain essential for investigation, validation, and decision-making.

## Skills Practiced

- Security Operations Center fundamentals
- Security orchestration and automation
- Incident response workflows
- Security playbook concepts
- Threat intelligence integration
- Vulnerability management
