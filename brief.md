Version: NAFATH-V4
Track: Cybersecurity

## Overview

A national service provider depends on software components, AI models, mobile applications, and internet routing, so a weakness in one layer can affect the wider service. Secure configuration keeps deployment settings and secrets out of source code. AI security considers attempts to manipulate inputs or training data. Mobile standards provide testable controls for protecting data and app behavior. Network protections such as RPKI help validate route origins, although they do not stop every routing attack. Cybersecurity teams identify, patch, and monitor vulnerabilities such as Log4Shell. A Software Bill of Materials (SBOM) helps connect a product to the components it contains. Together, these practices improve visibility across the software supply chain. This brief focuses on how Log4Shell became severe and how organizations can identify and remediate affected systems.

## Software

The Twelve-Factor App methodology recommends storing deployment-specific configuration in environment variables rather than hard-coding it into application code. This includes service addresses and credentials that vary between environments. Separating configuration makes applications easier to deploy consistently and reduces the chance that secrets are exposed in source repositories. Environment variables still require appropriate access controls and secure handling; for sensitive production credentials, a dedicated secrets manager may provide stronger lifecycle and auditing controls.
Resource: The Twelve-Factor App — III. Config - https://12factor.net/config

## AI

Adversarial machine-learning attacks can target different stages and goals. Evasion attacks alter inputs at inference time to cause incorrect predictions, while poisoning attacks compromise training data or the training process so the model learns harmful behavior. Privacy attacks attempt to reveal sensitive information about training data or model behavior. These categories require different mitigations, including robust evaluation, data provenance checks, access controls, and privacy testing; no single defense addresses every attack type.
Resource: NIST AI 100-2 E2025: Adversarial Machine Learning - https://csrc.nist.gov/pubs/ai/100/2/e2025/final

## Mobile

The OWASP Mobile Application Security Verification Standard (MASVS) is a framework of security requirements for mobile applications. It covers areas such as secure storage, cryptography, authentication, network communication, platform interaction, code quality, resilience, and privacy. A team can use the relevant controls to define security requirements, assess an app, and record evidence for each test. The Mobile Application Security Testing Guide (MASTG) can help testers perform technical checks. A checklist alone does not prove an app is secure.
Resource: OWASP Mobile Application Security Verification Standard (MASVS) - https://mas.owasp.org/MASVS/

## Networking

BGP helps networks exchange information about which autonomous systems can reach particular IP prefixes. In a route hijack, a network may announce an unauthorized route and attract traffic, potentially causing interception or disruption. Resource Public Key Infrastructure (RPKI) supports Route Origin Validation by checking route announcements against cryptographically signed Route Origin Authorizations. This can reject invalid origin announcements, but it does not validate every part of a route path or prevent all route leaks, compromised routers, or attacks on endpoints.
Resource: RFC 6811 — BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Cybersecurity

Log4Shell (CVE-2021-44228) was a critical remote-code-execution vulnerability affecting Apache Log4j 2, a widely used Java logging library. In vulnerable configurations, attacker-controlled text processed by the logger could trigger lookups that led to code execution. Its impact was amplified by Log4j’s widespread use and the potential compromise of confidentiality, integrity, and availability. The main remediation is to upgrade affected applications to an Apache-recommended fixed version and check for vulnerable copies bundled in dependencies, containers, and vendor software.
Resource: NVD — CVE-2021-44228 - https://nvd.nist.gov/vuln/detail/CVE-2021-44228

## Data

A Software Bill of Materials (SBOM) is an inventory of software components and their relationships for a particular product or release. It helps teams identify whether a component is affected when a vulnerability is disclosed and supports supply-chain risk management. Useful fields include the supplier, component name, version, unique identifiers where available, dependency relationships, SBOM author, and creation information. An SBOM is only useful when it is accurate, updated, and tied to the specific software version being assessed.
Resource: CISA — 2025 Minimum Elements for a Software Bill of Materials (SBOM) - https://www.cisa.gov/resources-tools/resources/2025-minimum-elements-software-bill-materials-sbom

## Misconception in My Track

## Open Question
