# Scope

## 1. Company Overview

**BiomedCloud** is a fictional healthcare technology (healthtech) startup in a growth
stage. The company provides a digital platform that allows partner laboratories and
healthcare providers to upload, store, and share diagnostic laboratory test results
with patients and referring physicians.

As a fast-growing startup, BiomedCloud has adopted **Amazon Web Services (AWS)** as
its primary cloud infrastructure provider to support scalability. However, due to its
growth stage, several IT governance and security processes are still maturing,
which is a common characteristic of early-stage technology companies and a relevant
condition for this assessment.

## 2. In-Scope Areas

This assessment covers the following domains within BiomedCloud's cloud environment:

- Identity and Access Management (IAM) and access control practices
- Multi-Factor Authentication (MFA) enforcement
- Data protection (encryption at rest and in transit)
- Public exposure of cloud storage resources (e.g., Amazon S3 buckets)
- Logging and monitoring practices
- Backup and disaster recovery procedures
- Change management practices
- Business continuity planning
- General security controls applicable to the AWS environment

<!-- NOVA SEÇÃO -->
## 3. Evidence Collection Approach

This assessment combines two types of analysis:

- **Documentary analysis**: applied to risks that are primarily organizational or
  procedural in nature (e.g., Change Management, Business Continuity), where
  evidence would typically consist of policies, procedures, or process
  documentation rather than technical configuration.

- **Hands-on technical validation**: applied to risks that can be directly observed
  in a cloud environment (e.g., IAM configuration, MFA enforcement, S3 bucket
  exposure, logging configuration). For these risks, real configurations were
  created and tested in a **personal AWS sandbox account**, and supporting
  screenshots are provided in the `evidence/` folder.

> **Important note:** The AWS sandbox account used in this project is fully
> isolated, contains no real patient data, and was created exclusively for the
> purposes of this educational project. Any resemblance between configurations
> shown and real production environments is coincidental.

## 4. Out-of-Scope Areas

The following areas are **not covered** in this assessment:

- Physical security of AWS data centers (managed under the AWS Shared
  Responsibility Model, not BiomedCloud's responsibility)
- Application-level source code review / secure coding practices
- Network penetration testing
- Human Resources and employee background check processes
- Financial and accounting controls (SOX-related, if applicable)
- Third-party laboratory systems outside BiomedCloud's direct AWS environment
- Production-scale infrastructure (this project uses a minimal, low-cost AWS
  sandbox setup, not a full replica of a production environment)

> **Note on the AWS Shared Responsibility Model:** AWS is responsible for the
> security *of* the cloud (infrastructure, hardware, physical facilities), while
> BiomedCloud, as the customer, is responsible for security *in* the cloud
> (configuration, access management, data protection). This assessment focuses
> exclusively on BiomedCloud's responsibilities under this model.

## 5. Data Classification

| Data Type | Classification | Regulatory Relevance |
|---|---|---|
| Laboratory test results | Sensitive Personal Data (Health Data) | LGPD (Art. 5, II) |
| Patient identification data | Personal Data | LGPD |
| System access logs | Internal / Operational | Supports audit evidence |

Laboratory test results are classified as **sensitive personal data** under
Brazil's General Data Protection Law (*Lei Geral de Proteção de Dados* — LGPD),
given their health-related nature. This classification directly influences the
**impact rating** assigned to risks involving this data throughout this assessment.

> Note: No real personal or health data was used at any point in this project.
> This classification is used solely to simulate realistic impact ratings.

## 6. Assessment Period

This assessment reflects BiomedCloud's cloud environment as of **September 2026**
and represents a point-in-time evaluation.