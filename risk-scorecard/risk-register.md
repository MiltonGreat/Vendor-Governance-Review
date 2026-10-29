# Risk Register

**Assessment:** Microsoft Azure Vendor Governance Review  
**Scoring:** Likelihood (1-5) × Impact (1-5)  
**Risk Ratings:** 1-4 Low, 5-9 Medium, 10-14 High, 15-25 Critical

---

## Risk Register

| Risk ID | Risk Description | Likelihood | Impact | Inherent Score | Current Controls | Residual Risk |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R-01** | Client misconfigures Azure PaaS (e.g., public storage blob, over-permissive RBAC) and exposes PII | 4 | 4 | **16 (High)** | Azure Security Benchmark available; Defender for Cloud can detect misconfigurations | **High** |
| **R-02** | Client assumes Azure's PCI DSS attestation covers client workloads, leading to compliance gap | 4 | 3 | **12 (High)** | Shared Responsibility Model documented; AKS PCI guidance exists | **Medium** |
| **R-03** | Client fails to enforce MFA/Conditional Access, allowing credential-based compromise of Azure tenant | 3 | 4 | **12 (High)** | Entra ID provides tools; client must configure | **Medium** |
| **R-04** | Azure's CSA CAIQ self-assessment is **deprecated** (last renewed April 2025), reducing supply chain visibility | 2 | 2 | **4 (Low)** | Request updated CAIQ directly; rely on SOC/ISO/PCI attestations instead | **Low** |
| **R-05** | Vendor lock-in limits ability to migrate if governance fails | 2 | 3 | **6 (Medium)** | Multi-cloud strategy optional; not a compliance risk | **Low** |

---

## Scoring Rationale

**R-01 (High):** The shared responsibility model explicitly states that for all cloud deployment types, the customer owns **data, accounts, and access management** [citation:2]. Azure provides tools (Azure Policy, Defender for Cloud) but does not auto-apply secure configurations. Public blob misconfigurations remain a leading cause of cloud data exposure.

**R-02 (High → Residual Medium):** Azure maintains PCI DSS attestation, but the Shared Responsibility Matrix makes clear that **customer workloads are not covered** by Azure's AOC [citation:19]. The residual risk is Medium because the guidance is available—the risk materializes only if the client fails to read it.

**R-03 (High → Residual Medium):** Entra ID provides MFA and Conditional Access, but enforcement is entirely client-configured [citation:2]. Microsoft cannot enforce MFA on the client's tenant.

**R-04 (Low):** The CAIQ deprecation is a **visibility gap, not a compliance failure** [citation:18]. Tier 1 evidence (PCI AOC) and Tier 2 evidence (CSA STAR Level 2) remain valid. The mitigation is a procurement request for the updated CAIQ.

**R-05 (Low):** Lock-in is a strategic consideration, not a compliance risk. It does not affect the security posture assessment.

---

## Overall Vendor Risk Rating

**MODERATE-LOW**

**Rationale:** Azure's platform controls are strong and independently attested (PCI DSS, SOC, ISO, CSA STAR Level 2). The residual risk is concentrated in **client configuration and governance**, which are controllable through policy enforcement, baseline assignment, and procurement conditions.

---

*This is a portfolio demonstration. Risk scores are the author's independent analysis.*
