---
layout: single
title: "Conducting A Security Audit"
excerpt: "Security audit for a fictional company named Botium Toys"
classes: wide
---

# Conduct A Security Audit

## Scenario

This scenario is based on a fictional company:

Botium Toys is a small U.S. business that develops and sells toys. The
business has a single physical location, which serves as their main
office, a storefront, and warehouse for their products. However, Botium
Toy's online presence has grown, attracting customers in the U.S. and
abroad. As a result, their information technology (IT) department is
under increasing pressure to support their online market worldwide.

The manager of the IT department has decided that an internal IT audit
needs to be conducted. She's worried about maintaining compliance and
business operations as the company grows without a clear plan. She
believes an internal audit can help better secure the company's
infrastructure and help them identify and mitigate potential risks,
threats, or vulnerabilities to critical assets. The manager is also
interested in ensuring that they comply with regulations related to
internally processing and accepting online payments and conducting
business in the European Union (E.U.).

The IT manager starts by implementing the National Institute of
Standards and Technology Cybersecurity Framework (NIST CSF),
establishing an audit scope and goals, listing assets currently managed
by the IT department, and completing a risk assessment. The goal of the
audit is to provide an overview of the risks and/or fines that the
company might experience due to the current state of their security
posture.

Your task is to review the IT manager's scope, goals, and risk
assessment report. Then, perform an internal audit by completing a
controls and compliance checklist.

## Botium Toys: Scope, goals, and risk assessment report

### Scope and goals of the audit

**Scope:** The scope is defined as the entire security program at Botium
Toys. This means all assets need to be assessed alongside internal
processes and procedures related to the implementation of controls and
compliance best practices.

**Goals:** Assess existing assets and complete the controls and
compliance checklist to determine which controls and compliance best
practices need to be implemented to improve Botium Toys' security
posture.

### Current assets

Assets managed by the IT Department include:

- On-premises equipment for in-office business needs

- Employee equipment: end-user devices (desktops/laptops,
  smartphones), remote workstations, headsets, cables, keyboards,
  mice, docking stations, surveillance cameras, etc.

- Storefront products available for retail sale on site and online;
  stored in the company's adjoining warehouse

- Management of systems, software, and services: accounting,
  telecommunication, database, security, ecommerce, and inventory
  management

- Internet access

- Internal network

- Data retention and storage

- Legacy system maintenance: end-of-life systems that require human
  monitoring

### Risk assessment

#### Risk description

Currently, there is inadequate management of assets. Additionally,
Botium Toys does not have all of the proper controls in place and may
not be fully compliant with U.S. and international regulations and
standards.

#### Control best practices

The first of the five functions of the NIST CSF is Identify. Botium Toys
will need to dedicate resources to identify assets so they can
appropriately manage them. Additionally, they will need to classify
existing assets and determine the impact of the loss of existing assets,
including systems, on business continuity.

#### Risk score

On a scale of 1 to 10, the risk score is 8, which is fairly high. This
is due to a lack of controls and adherence to compliance best practices.

#### Additional comments

The potential impact from the loss of an asset is rated as medium,
because the IT department does not know which assets would be at risk.
The risk to assets or fines from governing bodies is high because Botium
Toys does not have all of the necessary controls in place and is not
fully adhering to best practices related to compliance regulations that
keep critical data private/secure. Review the following bullet points
for specific details:

- Currently, all Botium Toys employees have access to internally
  stored data and may be able to access cardholder data and customers'
  PII/SPII.

- Encryption is not currently used to ensure confidentiality of
  customers' credit card information that is accepted, processed,
  transmitted, and stored locally in the company's internal database.

- Access controls pertaining to least privilege and separation of
  duties have not been implemented.

- The IT department has ensured availability and integrated controls
  to ensure data integrity.

- The IT department has a firewall that blocks traffic based on an
  appropriately defined set of security rules.

- Antivirus software is installed and monitored regularly by the IT
  department.

- The IT department has not installed an intrusion detection system
  (IDS).

- There are no disaster recovery plans currently in place, and the
  company does not have backups of critical data.

- The IT department has established a plan to notify E.U. customers
  within 72 hours if there is a security breach. Additionally, privacy
  policies, procedures, and processes have been developed and are
  enforced among IT department members/other employees, to properly
  document and maintain data.

- Although a password policy exists, its requirements are nominal and
  not in line with current minimum password complexity requirements
  (e.g., at least eight characters, a combination of letters and at
  least one number; special characters).

- There is no centralized password management system that enforces the
  password policy's minimum requirements, which sometimes affects
  productivity when employees/vendors submit a ticket to the IT
  department to recover or reset a password.

- While legacy systems are monitored and maintained, there is no
  regular schedule in place for these tasks and intervention methods
  are unclear.

- The store's physical location, which includes Botium Toys' main
  offices, store front, and warehouse of products, has sufficient
  locks, up-to-date closed-circuit television (CCTV) surveillance, as
  well as functioning fire detection and prevention systems.

## Controls and compliance checklist

**_Completed by:_ Steven Brauner**

### Controls assessment checklist

To complete the controls assessment checklist, refer to the information
provided in the _Scope, goals, and risk assessment report_.

Then, select "yes" or "no" to answer the question: _Does Botium Toys
currently have this control in place?_

| Yes | No  |                                Control                                 | Explanation                                                                                                                                                                                                      |
| :-: | :-: | :--------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     |  X  |                            Least privilege                             | All employees have access to customer data. Access should be<br>limited by role to reduce risk from unauthorized access.                                                                                         |
|     |  X  |                        Disaster recovery plans                         | No plan currently in place. Needed for business continuity.                                                                                                                                                      |
|     |  X  |                           Password policies                            | Password policy exists but the requirements are nominal. Need<br>to update to meet minimum standards.                                                                                                            |
|     |  X  |                          Separation of duties                          | Access controls have not been implemented to ensure separation<br>of duties.                                                                                                                                     |
|  X  |     |                                Firewall                                | The firewall is appropriately configured to filter unwanted traffic.                                                                                                                                             |
|     |  X  |                    Intrusion detection system (IDS)                    | Need to install IDS to detect potential intrusions.                                                                                                                                                              |
|     |  X  |                                Backups                                 | No backups currently in place. Need to establish a backup plan<br>to ensure data integrity.                                                                                                                      |
|  X  |     |                           Antivirus software                           | Currently installed and monitored to detect and quarantine known<br>threats.                                                                                                                                     |
|     |  X  | Manual monitoring, maintenance,<br>and intervention for legacy systems | While systems are monitored and maintained, there is no regular<br>schedule in place for these tasks. This is necessary to avoid<br>threats, risks, or vulnerabilities due to out-of-date systems.               |
|     |  X  |                               Encryption                               | Encryption is not currently used to ensure confidentiality of<br>customer data. Encryption should be used to provide confidentiality to<br>sensitive data.                                                       |
|     |  X  |                       Password management system                       | No system is in place. This is needed to reduce password fatigue.                                                                                                                                                |
|  X  |     |                 Locks (offices, storefront, warehouse)                 | Locks are sufficient to prevent unauthorized access to the store,<br>office, and warehouse.                                                                                                                      |
|  X  |     |             Closed-circuit television (CCTV) surveillance              | CCTV surveillance is sufficient to monitor the store, office,<br>and warehouse. CCTV is both a preventative and detective control,<br>reducing risks, and useful to inform on events that have already occurred. |
|  X  |     |   Fire detection/prevention<br>(fire alarm, sprinkler system, etc.)    | The fire detection/prevention is sufficient to detect and prevent<br>fires. This is needed to prevent damage to physical assets.                                                                                 |

### Compliance checklist

To complete the compliance checklist, refer to the information provided
in the _Scope, goals, and risk assessment report_.

Then, select "yes" or "no" to answer the question: _Does Botium Toys
currently adhere to this compliance best practice?_

#### Payment Card Industry Data Security Standard (PCI DSS)

| Yes | No  |                                                   Best practice                                                    | Explanation                                                                                                   |
| :-: | :-: | :----------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------ |
|     |  X  |                    Only authorized users have access to<br>customers' credit card information.                     | Currently all employees have access to credit card information.<br>Need to implement lease priviege controls. |
|     |  X  | Credit card information is stored, accepted,<br>processed, and transmitted internally,<br>in a secure environment. | Currently credit card information is not in a secured environment.<br>Need to implement encryption controls.  |
|     |  x  |     Implement data encryption procedures to better<br>secure credit card transaction<br>touchpoints and data.      | Currently credit card information is not encrypted. Need to<br>implement encryption controls.                 |
|     |  X  |                                     Adopt secure password management policies.                                     | Currently no password management system is in place. Need to<by>implement this policy.                        |

#### General Data Protection Regulation (GDPR)

| Yes | No  |                                                      Best practice                                                      | Explanation                                                                                               |
| :-: | :-: | :---------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------- |
|     |  X  |                                      E.U. customers' data is kept private/secured.                                      | Currently all E.U. customers' data is not kept private/secured.<br>Need to implement encryption controls. |
|  X  |     | There is a plan in place to notify E.U. customers<br>within 72 hours if their data is<br>compromised/there is a breach. | Currently there is a plan in place                                                                        |
|     |  X  |                                   Ensure data is properly classified and inventoried.                                   | Currently data is properly inventoried/listed, but not classified.                                        |
|  X  |     |             Enforce privacy policies, procedures, and processes<br>to properly document and maintain data.              | These policies, procedures, and processes are enforced.                                                   |

#### System and Organizations Controls (SOC type 1, SOC type 2)

| Yes | No  |                                         Best practice                                         | Explanation                                                                                                                |
| :-: | :-: | :-------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------- |
|     |  X  |                             User access policies are established.                             | All employees have access to data. Need to implement least privilege<br>and separation of duties controls.                 |
|     |  X  |                      Sensitive data (PII/SPII) is confidential/private.                       | PII and SPII are not protected. Need to implement encryption controls.                                                     |
|  X  |     | Data integrity ensures the data is consistent,<br>complete, accurate, and has been validated. | Controls are in place to ensure data is consistent, complete, accurate,<br>and has been validated.                         |
|     |  X  |                   Data is available to individuals authorized to access it.                   | While data is available to authorized users, there are no controls to<br>ensure it is only accessible to authorized users. |

### Recommendations (optional)

This section is _optional_ and can be used to provide a summary of recommendations to the IT manager regarding which controls and/or compliance best practices Botium Toys needs to implement, based on the risk posed if not implemented in a timely manner.

In this section, provide recommendations, related to controls and/or compliance needs, that your IT manager could communicate to stakeholders to reduce risks to assets and improve Botium Toys' security posture.

#### Botium Toys needs to implement the following controls:

- Lease privilege and separation of duties controls
- Encryption controls
- Password policies
- A password management system
- Disaster recovery plans
- An Intrusion Detection System (IDS)
- Keep backup copies of critical data
- Ongoing maintenance of legacy systems

#### Botium Toys currently has a compliance issue with the PCI DSS, the GDPR, and the SOC. The IT manager should recommend that the IT department implement the following:

- Lease privilege and separation of duties controls
- Encryption controls
- Properly classify assets
- Secure password policies
