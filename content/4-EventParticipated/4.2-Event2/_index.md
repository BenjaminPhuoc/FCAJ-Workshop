---
title: "Event 2"
date: 2026-06-11
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# SUMMARY REPORT: CLOUD ARCHITECT & TECH TALK EVENT (JUNE 11)

## 1. Brief Description of Event Content & Core Activities
The event ran in two parts: the Cloud Architect Competition Finals, followed by a series of in-depth Tech Talks from 3 speakers representing different tech companies.

### A. Activity 1: Cloud Architect Competition Finals ("Ao Lang" Award)
- **Format:** A scenario-based multiple-choice contest on cloud architecture between the top two finalist teams (KLK AST Team vs. Ngu Dai Hiep Team).
- **Core Topics Covered:** Real-world AWS engineering scenarios, including:
  - Choosing IaaS models (EC2) and following compliant decommissioning processes for storage devices.
  - Enforcing least-privilege access for S3 buckets.
  - High-throughput UDP load balancing for multiplayer games paired with a key-value database (NLB + DynamoDB).
  - Automated EC2 error remediation using CloudWatch Logs, Metric Filters & Alarms.
  - Securely serving content from S3 via CloudFront using Origin Access Control (OAC).
  - Designing low-latency, high-bandwidth hybrid connectivity between on-prem data centers and multi-region VPCs (Direct Connect Gateway).
  - Migrating a large-scale MySQL database (25TB) from on-prem to AWS with minimal downtime (AWS DMS / DataSync / Aurora Replication).
  - Automating AMI/EC2 updates with CloudFormation and Systems Manager Parameter Store.

### B. Activity 2: Expert Talk Series

#### Topic 1: Applying AI in Cloud Security with AWS Security Agent
*(Speaker: Mr. Thinh — DevOps/DevSecOps Engineer)*
- Broke down the limitations of traditional pentesting: expensive ($5,000–$20,000 per run), dependent on people, and slow.
- Introduced the AWS Security Agent, which uses multi-agent AI / Bedrock to automate design security reviews (checking architecture against PCI-DSS and the Well-Architected Framework), code reviews (CI/CD integration, PR auditing on GitHub/GitLab), and automated system pentesting.
- Called out the current gaps: no automated handling yet for complex MFA flows (SSO, email OTP) or specialized protocols like mTLS.

#### Topic 2: SLA Governance & Monitoring Systems in Enterprise Practice
*(Speaker: Mr. Nam — Infrastructure/Reliability Engineer)*
- Walked through why SLAs matter and what it means to actually honor commitments to customers.
- Made the point that healthy infrastructure doesn't guarantee a healthy user experience if the application itself has logical connection failures.
- Risk governance lifecycle: Identify Risk → Monitor Signal → Response (SOP/SNS) → Log & Improve.
- Live demo: building a CloudWatch dashboard and configuring disconnection alerts between EC2 (backend) and RDS PostgreSQL via AWS SNS.

#### Topic 3: Roadmap & Prep Strategy for the AWS Certified Cloud Practitioner (CLF-C02)
*(Speaker: Mr. Huy)*
- Overview of the AWS certification tiers (Foundational, Associate, Professional, Specialty).
- CLF-C02 exam structure: 65 multiple-choice questions, 120 minutes (plus a 30-minute extension for non-native English speakers), 700/1000 passing score, 3-year validity, $100 fee.
- Domain weighting: Cloud Concepts (24%), Security & Compliance (30%), Cloud Technology & Services (34%), Billing & Pricing (12%).
- Exam tactics: process of elimination, keyword mapping, hands-on practice via AWS Free Tier, and using the "Flag for Review" feature.

## 2. Key Results & Value Gained

### A. Professional Knowledge & Lessons Learned
- **Cloud Architecture & Infrastructure:** Got a firmer grasp on orchestrating advanced AWS services (Direct Connect, CloudFront OAC, Auto Scaling, SQS, DMS) for large-scale infrastructure that needs both high availability and cost efficiency.
- **Security Automation (DevSecOps):** Saw firsthand how generative AI / multi-agent frameworks are starting to reshape vulnerability auditing and security-by-design from the planning stage onward.
- **Enterprise Operations Mindset (SRE/Reliability):** Took away that monitoring isn't really about keeping dashboards "green" — it's about keeping the customer journey uninterrupted and honoring SLA commitments.

### B. Newly Acquired Skills
- **Hands-on Monitoring Configuration:** Learned to build custom CloudWatch metric alarms, wire up alert matrices through AWS SNS, and bridge health checks between the EC2 and RDS tiers.
- **International Certification Prep:** Picked up keyword analysis, process-of-elimination strategy, and time management tactics for the AWS Practitioner/Associate exams.

## 3. Practical Participation Summary & Accumulated Experience
- **Absorbing Real-World Practices:** Attending in person helped connect academic theory to the kind of incidents companies actually deal with — backend-to-database disconnects, broken automation scripts, or the financial risk of missing an SLA.
- **Soft Skills Refinement:** Sharpened critical thinking while working through the competition's architecture scenarios, and picked up some presentation habits watching senior engineers do live troubleshooting.
- **Career Path Orientation:** Came away with a clearer roadmap for Cloud/DevOps learning, with concrete AWS certification milestones to strengthen my professional profile.

![Event2](/images/4-EventParticipated/event_11-6-26/1.png)
![Event2](/images/4-EventParticipated/event_11-6-26/2.png)
![Event2](/images/4-EventParticipated/event_11-6-26/3.png)
![Event2](/images/4-EventParticipated/event_11-6-26/4.png)
![Event2](/images/4-EventParticipated/event_11-6-26/5.png)
![Event2](/images/4-EventParticipated/event_11-6-26/6.png)
![Event2](/images/4-EventParticipated/event_11-6-26/7.png)
![Event2](/images/4-EventParticipated/event_11-6-26/8.png)
