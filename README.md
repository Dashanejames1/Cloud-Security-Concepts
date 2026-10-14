# Cloud-Security-Concepts


**Author:** Dashane James  
**Lab Environment:** VMware Workstation | Kali Linux | Metasploitable 2
**Purpose:** Build the frameworks an analyst needs to reason about cloud risk — who is responsible for what, how AWS detects threats natively, and where organizations most often leave themselves exposed.
**Status:** 🔵 Completed

---

## 📋 Overview

This repository documents the core cloud security concepts and AWS-native tools an analyst needs to reason about cloud risk: the shared responsibility model, the logging and detection services AWS provides, the most common cloud misconfigurations, cloud security posture management (CSPM), and how security responsibility shifts across the IaaS, PaaS, and SaaS service models.


---

---

## 🔬 Tasks / Assessments Performed

### 1. AWS Shared Responsibility model explained.(What AWS secures vs what users secure.)
For this task 


# Output

AWS secures everything physical and infrastructural — data centers, hardware, networking, the hypervisor, and the underlying engines of managed services like RDS. You secure everything inside your environment — your data, your IAM users and roles, the OS on any EC2 instance you run, your application code, your security group rules, and encryption of data at rest and in transit. The line is: AWS owns the cloud itself, you own what you put in it.

**Findings:**


### 2. Explaining CloudTrail(logging), GuardDuty (threat detection), and security Hub (CSPM/SIEM)
[]


# Output

CloudTrail logs every API call made in your AWS account — who did it, when, from where. It’s your audit trail. GuardDuty reads those logs automatically and uses machine learning to flag malicious behavior — compromised credentials, crypto mining, unusual API patterns — without you needing to configure anything. Security Hub pulls findings from GuardDuty, Inspector, Macie, and third-party tools into one dashboard and maps them against CIS and NIST benchmarks, functioning as both a CSPM and a lightweight SIEM aggregator.


**Findings:**


### 3. Common cloud misconfigs: public S3 buckets, over-permissive IAM, and no MFA on root.
[] 



# Output

The three biggest: a public S3 bucket exposes your data to anyone on the internet; over-permissive IAM means any attacker with a foothold can escalate to admin-level access; no MFA on the root account means a phished or leaked password gives an attacker complete control of the entire AWS account. Secondary ones include unrestricted security groups open to 0.0.0.0/0 and unencrypted EBS volumes or S3 buckets.

```

**Findings:**



## 4. CSPM (Cloud Security Posture Management). What it does and when you use it.


# Output

CSPM continuously scans your cloud environment for misconfigurations and drift from your security baseline — checking IAM policies, storage permissions, network rules, encryption settings, and compliance alignment against frameworks like CIS, NIST, and PCI DSS. You use it for ongoing compliance monitoring, catching configuration changes that introduce risk after a deployment, and generating audit-ready posture reports. In AWS the native tool is Security Hub; third-party options include Prisma Cloud, Wiz, and Orca.


**Findings:** 

### 5. [Iaas vs Paas vs SAAS security responsibility differences.]

For this task

### Output

In IaaS (like EC2) you own the OS, runtime, application, and data — AWS only handles the physical layer and hypervisor. In PaaS (like Elastic Beanstalk) AWS takes over the OS and runtime, leaving you responsible for the application and data. In SaaS (like WorkMail) AWS manages nearly everything including the application — you are only responsible for your data and IAM. Across all three models, data and identity are always yours.

---


---

## 🔑 Technical Notes

Shared responsibility is the anchor concept — most cloud exam questions and real incidents trace back to a customer-side responsibility that was misread as AWS's.
The detection stack layers: CloudTrail records → GuardDuty detects → Security Hub aggregates. Knowing which one does what is a common exam distinction.
Responsibility shrinks as you move up the stack (IaaS → PaaS → SaaS), but data and identity never leave the customer.

```

---

## 📌 About This Project

This repository is the cloud module of my cybersecurity portfolio. Where the other labs are hands-on against a local target, this one builds the cloud frameworks that modern SOC work and the CySA+ exam both assume, rounding out the on-prem skills with the shared-responsibility and cloud-posture thinking employers expect.

## Related repositories:

Vulnerability-Management-Deep-Review — Scoring, validating, and prioritizing vulnerabilities (the risk-judgment counterpart to CSPM here)
Incident-Response-Report — Worked a confirmed compromise through the full IR lifecycle
Full-Kill-Chain-Red-and-Blue-Teams — Ties attack and detection together end to end

---

## 👤 Author

**Dashane James**  
Senior Field Service Technician → Cybersecurity Analyst  
📍 Yonkers, NY  
🎓 B.S. Information Technology — SUNY Canton  
🏆 CompTIA Security+ | CySA+ (In Progress)  
🔗 [GitHub](https://github.com/Dashanejames1) | [Zero Trust Cyber Security Brand](https://www.instagram.com/zerotrust_cybersecurity)

---

*This repository is part of an active portfolio demonstrating hands-on cybersecurity skills. All lab work performed in isolated environments for educational purposes.*
