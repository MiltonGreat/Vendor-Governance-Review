# Evidence Register

**Assessment:** Microsoft Azure Vendor Governance Review  
**Client Context:** Series B Fintech (Fictional)  

---

## Evidence Hierarchy Rationale

| Tier | Evidence Type | Reliability | Why It Ranks Here |
| :--- | :--- | :--- | :--- |
| **Tier 1** | Regulatory Attestations (PCI DSS QSA assessment, SOC reports) | **Highest** | Independent third-party audit; legally defensible; source of truth for version and scope |
| **Tier 2** | Certifications (ISO 27001, CSA STAR Level 2) | **High** | Independent certification body; periodic renewal required |
| **Tier 3** | Self-Assessments (CSA CAIQ) | **Medium** | Vendor-attested; **deprecated status reduces reliability**; must be corroborated |
| **Tier 4** | Vendor Marketing / Learn Documentation | **Low-Medium** | Convenient for implementation guidance; not independently verified |

---

## Evidence Register

| ID | Source | URL | Retrieved | Reliability | What It Establishes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **E-01** | Microsoft Service Trust Portal (PCI DSS) | https://servicetrust.microsoft.com | [Date] | **Tier 1 (High)** | Azure maintains PCI DSS attestation via QSA; PCI DSS packages and Shared Responsibility Matrices downloadable [citation:1][citation:19] |
| **E-02** | Azure Shared Responsibility Model | https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility | [Date] | **Tier 1 (High)** | Defines client vs. Microsoft responsibilities; customer always owns data, identities, accounts, and access management [citation:2] |
| **E-03** | Azure Security Benchmark (ASB) v3 | https://learn.microsoft.com/en-us/security/benchmark/azure/overview-v3 | [Date] | **Tier 2 (High)** | Prescriptive security controls mapped to PCI DSS v3.2.1, CIS v8, and NIST SP 800-53; provides configuration baselines [citation:3][citation:10] |
| **E-04** | CSA STAR Registry — Microsoft Azure | https://cloudsecurityalliance.org/star/registry/microsoft/services/microsoft-azure | [Date] | **Tier 3 (Medium)** | Azure holds STAR Level 2 (Certification v4.0). **CAIQ Self-assessment v4.0.2 last renewed April 7, 2025 and is marked Deprecated** [citation:18] |
| **E-05** | CSA STAR Self-Assessment Documentation (Microsoft) | Microsoft CSA STAR PDF | [Date] | **Tier 3 (Medium)** | Microsoft publishes CAIQ and CCM-based reports; STAR Level 1 Self-Assessment available [citation:4] |
| **E-06** | Azure PCI DSS 4.0.1 Guidance (AKS) | https://learn.microsoft.com/en-us/azure/aks/pci-intro | [Date] | **Tier 2 (High)** | Microsoft completes annual PCI DSS QSA assessment; customer must still define shared responsibility in policy; AKS reference architecture is **not** a substitute for QSA attestation [citation:5] |
| **E-07** | Microsoft Trust Center | https://www.microsoft.com/en-us/trust-center | [Date] | **Tier 4 (Low-Medium)** | Central marketing hub linking to compliance offerings; useful for navigation, not independent verification |

---

## Critical Evidence Finding

**E-04 (CSA CAIQ Deprecation):** The Azure CAIQ self-assessment was last renewed on **April 7, 2025**, and the CSA registry now marks it as **Deprecated** [citation:18]. This does **not** mean Azure is non-compliant—it means the self-attestation has not been updated within its validity period. For this review, the deprecation **reduces the reliability of the CAIQ as Tier 3 evidence** and increases the importance of Tier 1 attestations (E-01) and Tier 2 certifications (E-04 STAR Level 2) in the final risk score.

**Recommended Action:** Request the current CAIQ directly from Microsoft during procurement due diligence.

---

*This is a portfolio demonstration. It is not legal, compliance, or procurement advice.*
