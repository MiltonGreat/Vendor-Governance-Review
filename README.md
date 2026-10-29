# Vendor Governance Review: Microsoft Azure (PaaS/IaaS)

**Client Context:** Series B Fintech (Fictional)  
**Classification:** Portfolio Demonstration — Not a Formal Audit

---

## Executive Summary

This review assesses Microsoft Azure as a prospective cloud infrastructure provider for a fictional Series B fintech processing payments. The client's risk profile is defined by **low tolerance for PII exposure** and **mandatory PCI DSS compliance**.

**Overall Vendor Risk Rating: MODERATE-LOW**

Azure demonstrates strong regulatory compliance posture (PCI DSS, SOC 1/2/3, ISO 27001) and a mature shared responsibility model. However, the client retains **significant residual responsibility** for configuring the platform securely—particularly around identity management, network controls, and data classification. The primary risk is not vendor failure, but **client misconfiguration**.

**Procurement Recommendation: APPROVE WITH CONDITIONS.** Proceed with Azure, subject to mandatory contract clauses and pre-deployment control implementation (detailed in `/recommendations`).

---

## Scope & Methodology

| Element | Detail |
| :--- | :--- |
| **Vendor** | Microsoft Azure (PaaS and IaaS services) |
| **Client (Fictional)** | Series B fintech, payment processing, Canadian operations |
| **Regulatory Scope** | PCI DSS 4.0.1 (cardholder data environment), PIPEDA (Canadian privacy) |
| **Framework** | NIST CSF (ID.SC, PR.AC, PR.DS), CSA CCM |
| **Evidence Sources** | Microsoft Trust Center, Service Trust Portal, CSA STAR Registry, Microsoft Learn documentation |
| **Scoring** | Likelihood (1-5) × Impact (1-5); 0=Met, 1=Partial, 2=Gap, 3=Critical Gap |

**Disclaimer:** The client organization is fictional. All claims about Azure's controls are sourced from publicly available Microsoft and CSA documentation. Risk scores and procurement recommendations are the author's independent analysis.

---

## Key Findings (Summary)

| Risk ID | Finding | Inherent Score | Residual Risk |
| :--- | :--- | :--- | :--- |
| R-01 | Client misconfiguration of Azure PaaS services can expose PII despite Azure's platform security | 16 (High) | **High** |
| R-02 | PCI DSS compliance is a **shared responsibility**; Azure's attestation does not cover client workloads | 15 (High) | **Medium** |
| R-03 | Identity and access management is client-controlled; Azure provides tools but not guarantees | 12 (Medium) | **Medium** |
| R-04 | Azure's CSA STAR CAIQ self-assessment is **deprecated** (last renewed April 2025) | 6 (Low) | **Low** |

---

## Navigation

| Folder | Contents |
| :--- | :--- |
| [`/evidence`](./evidence/) | Links to public sources, with retrieval dates and reliability ratings |
| [`/control-gap-analysis`](./control-gap-analysis/) | Control-by-control assessment against PCI DSS and NIST CSF |
| [`/risk-scorecard`](./risk-scorecard/) | Full risk register with likelihood, impact, and scoring rationale |
| [`/recommendations`](./recommendations/) | Procurement recommendation and mandatory contract clauses |

---

## Why This Review Exists

Most vendor governance portfolios use fully simulated scenarios. This review uses a **real vendor** (Microsoft Azure) with **publicly verifiable evidence** to demonstrate that the author can:

1. **Research** a vendor's published security posture.
2. **Evaluate** claims against a recognized framework.
3. **Distinguish** between platform-level attestations and client-level responsibilities.
4. **Produce** actionable procurement recommendations grounded in evidence.

The fictional client provides business context without requiring access to confidential data.

---

## Sources (Selected)

| Source | URL | Reliability |
| :--- | :--- | :--- |
| Microsoft Trust Center | https://www.microsoft.com/en-us/trust-center | High |
| Azure Compliance Offerings | https://learn.microsoft.com/en-us/azure/compliance/offerings/ | High |
| CSA STAR Registry — Microsoft Azure | https://cloudsecurityalliance.org/star/registry/microsoft/services/microsoft-azure | Medium-High |
| Azure Shared Responsibility Model | https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility | High |
| Azure Security Benchmark | https://learn.microsoft.com/en-us/security/benchmark/azure/ | High |

---

*This is a portfolio demonstration. It is not legal, compliance, or procurement advice.*
