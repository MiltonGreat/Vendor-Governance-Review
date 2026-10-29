# Third-Party AI Vendor Assessment
### Microsoft Azure (PaaS/IaaS)

**Client:** Series B Fintech (Fictional) — Payment Processing  
**Assessment Type:** Pre-Procurement Vendor Risk Assessment  
**Framework:** NIST CSF (ID.SC, PR.AC, PR.DS) + PCI DSS 4.0.1  
**Classification:** Portfolio Demonstration — Not a Formal Audit

---

## Business Objective

The client is a Series B fintech preparing to migrate its payment processing workloads to a public cloud provider. The decision carries two non-negotiable business constraints:

1. **Low tolerance for PII exposure.** A data breach would trigger regulatory notification obligations, reputational damage, and potential loss of payment network privileges.
2. **Mandatory PCI DSS 4.0.1 compliance.** The client must demonstrate compliance for its cardholder data environment (CDE) regardless of where that environment is hosted.

**The business question this review answers:**

> *Can we safely entrust our payment workloads to Microsoft Azure, and if so, under what conditions?*

This review does not ask "Is Azure secure?" Azure is secure. The review asks a narrower, more useful question: **"What must we do, contractually and operationally, to ensure that Azure's security posture extends to our workloads?"**

---

## Executive Summary

**Overall Vendor Risk Rating: MODERATE-LOW**

**Procurement Recommendation: APPROVE WITH CONDITIONS**

Azure demonstrates strong, independently attested platform security (PCI DSS, SOC 1/2/3, ISO 27001, CSA STAR Level 2). The Shared Responsibility Model is clearly documented, and the Azure Security Benchmark provides prescriptive configuration guidance.

However, the business risk is not concentrated in Azure's platform. It is concentrated in **client configuration and governance**. Azure provides the tools; the client bears the responsibility for using them correctly.

**The five conditions in this review are the difference between a compliant deployment and a preventable breach.**

---

## Why This Review Exists (Methodology)

This review follows a four-step governance process:

| Step | What It Does | Where It Lives |
| :--- | :--- | :--- |
| **1. Evidence Collection** | Gather publicly verifiable vendor security documentation and rank it by reliability | [`/evidence`](./evidence/) |
| **2. Control Assessment** | Map the vendor's controls against the client's regulatory obligations | [`/control-gap-analysis`](./control-gap-analysis/) |
| **3. Risk Scoring** | Quantify residual risk after accounting for available controls | [`/risk-scorecard`](./risk-scorecard/) |
| **4. Procurement Decision** | Translate findings into contract conditions and go/no-go criteria | [`/recommendations`](./recommendations/) |

**A note on evidence hierarchy:** Not all vendor claims are equal. This review ranks evidence by reliability, from independent regulatory attestations (Tier 1) down to vendor marketing pages (Tier 4). The most consequential finding in this review is that Azure's CSA CAIQ self-assessment is **deprecated** —which reduces its evidentiary value and shifts weight to the Tier 1 attestations.

---

## Key Findings

| Risk ID | Finding | Inherent Score | Residual Risk |
| :--- | :--- | :--- | :--- |
| **R-01** | Client misconfiguration of Azure PaaS services can expose PII despite Azure's platform security | 16 (High) | **High** |
| **R-02** | PCI DSS compliance is a shared responsibility; Azure's attestation does not cover client workloads | 12 (High) | **Medium** |
| **R-03** | Identity and access management is client-controlled; Azure provides tools but not guarantees | 12 (High) | **Medium** |
| **R-04** | Azure's CSA STAR CAIQ self-assessment is deprecated (last renewed April 2025) | 4 (Low) | **Low** |
| **R-05** | Vendor lock-in limits migration flexibility | 6 (Medium) | **Low** |

**Interpretation for the business:** The two highest residual risks (R-01, R-02) are both **client-controlled**. This is good news for the procurement decision—it means the risks are manageable through contract terms and pre-deployment controls, not dependent on Azure changing its behavior.

---

## The Five Conditions for Approval

Approval is conditional on the following controls being in place before PII is processed:

| # | Condition | Addresses |
| :--- | :--- | :--- |
| **1** | Assign Azure Security Benchmark policies to all subscriptions | R-01 |
| **2** | Obtain the current CAIQ directly from Microsoft | R-04 |
| **3** | Enforce MFA and Conditional Access for all admin roles | R-03 |
| **4** | Maintain a client-side PCI DSS compliance program | R-02 |
| **5** | Classify data and configure DLP before PII ingestion | R-01 |

Full contract clause language is in [`/recommendations/procurement-recommendation.md`](./recommendations/procurement-recommendation.md).

---

## What This Review Demonstrates

| Skill | Where It Appears |
| :--- | :--- |
| **Evidence-based judgment** | The evidence hierarchy ranks regulatory attestations above vendor self-assessments |
| **Regulatory fluency** | PCI DSS 4.0.1 and NIST CSF are applied as assessment criteria, not decoration |
| **Risk quantification** | The risk register converts findings into likelihood × impact scores with rationale |
| **Commercial translation** | The procurement recommendation converts risk findings into contract clauses and go/no-go conditions |
| **Research rigor** | All vendor claims are sourced from public Microsoft and CSA documentation with retrieval dates |

---

## Important Disclaimer

The client organization described in this review is **fictional**. Microsoft Azure is a real vendor, and all claims about Azure's controls are sourced from publicly available Microsoft and Cloud Security Alliance documentation. Risk scores, control gap ratings, and procurement recommendations are the author's independent analysis.

This is a **portfolio demonstration**. It is not legal, compliance, or procurement advice, and it has not been reviewed by Microsoft, a QSA, or any regulatory body.

---

## Sources (Selected)

| Source | Reliability Tier |
| :--- | :--- |
| Microsoft Service Trust Portal (PCI DSS AOC) | Tier 1 |
| Azure Shared Responsibility Model | Tier 1 |
| Azure Security Benchmark v3 | Tier 2 |
| CSA STAR Registry — Azure (STAR Level 2) | Tier 2 |
| CSA CAIQ Self-Assessment (Azure) — **Deprecated** | Tier 3 |
| Microsoft Trust Center | Tier 4 |

Full register with URLs and retrieval dates: [`/evidence/evidence-register.md`](./evidence/evidence-register.md)
