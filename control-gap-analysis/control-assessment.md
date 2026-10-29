# Control Gap Analysis

**Assessment:** Microsoft Azure Vendor Governance Review  
**Framework:** NIST CSF (ID.SC, PR.AC, PR.DS) + PCI DSS 4.0.1  
**Scoring:** 0 = Met, 1 = Partial, 2 = Gap, 3 = Critical Gap

---

## Control Assessment Matrix

| Control ID | Requirement (Source) | Azure Control (Platform) | Client Responsibility | Gap Score | Rationale |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **ID.SC-1** | Supply chain risk management processes established (NIST CSF) | Azure publishes compliance documentation; Service Trust Portal provides attestations | Client must define vendor governance program and assess Azure as critical supplier | **0 (Met)** | Azure's public attestations satisfy the supplier-assessment input; client governance is a standard internal control [citation:2] |
| **ID.SC-2** | Suppliers assessed using cyber supply chain risk assessment (NIST CSF) | Azure PCI DSS AOC and SOC reports available via Service Trust Portal | Client must download and review the AOC; cannot rely on marketing pages alone | **1 (Partial)** | Evidence exists but requires active retrieval; **CAIQ is deprecated**, reducing self-attestation value [citation:18][citation:19] |
| **ID.SC-3** | Contracts implement security measures (NIST CSF) | Microsoft publishes Shared Responsibility Matrix | Client must incorporate matrix into contract and define audit rights | **1 (Partial)** | Matrix available but **not automatically contractual**; client must negotiate [citation:2][citation:19] |
| **PR.AC-1** | Identities and credentials managed (NIST CSF) | Entra ID provides identity platform, MFA, Conditional Access | **Client fully responsible** for account lifecycle, role assignment, MFA enforcement | **2 (Gap)** | Platform tools exist; misconfiguration is the primary risk vector [citation:2] |
| **PR.AC-3** | Remote access managed (NIST CSF) | Azure provides VPN Gateway, Bastion, Conditional Access | Client must configure and monitor remote access controls | **2 (Gap)** | Client-configured; no Azure default that prevents misconfiguration |
| **PR.DS-1** | Data-at-rest protected (NIST CSF) | Azure provides default encryption at rest for most services | Client must classify data, manage keys (Key Vault), and configure service-specific encryption | **2 (Gap)** | Default encryption exists, but **PII exposure risk is client-configured** (e.g., public blob misconfiguration) [citation:2] |
| **PR.DS-2** | Data-in-transit protected (NIST CSF) | Azure supports TLS; services enforce HTTPS by default | Client must enforce TLS on custom applications and PaaS configurations | **1 (Partial)** | Platform enforces minimums; application-layer configuration remains client responsibility |
| **PCI-1** | Network security controls (PCI DSS Req 1) | Azure provides VNet, NSG, Azure Firewall | Client must design and configure CDE segmentation | **1 (Partial)** | Capability exists; **client configuration is the risk** [citation:5] |
| **PCI-2** | Secure configurations (PCI DSS Req 2) | Azure Security Benchmark provides baselines; Azure Policy can enforce | Client must assign and monitor baseline policies | **1 (Partial)** | Baselines available but **not auto-applied**; client must implement [citation:3] |
| **PCI-12** | Information security policy (PCI DSS Req 12) | Microsoft completes annual PCI DSS QSA assessment | Client must define shared responsibility in policy and review annually | **0 (Met)** | Azure's attestation is documented; client policy is a standard governance task [citation:19] |

---

## Control Gap Summary

| Gap Severity | Count | Controls |
| :--- | :--- | :--- |
| **Critical (3)** | 0 | None |
| **Gap (2)** | 4 | PR.AC-1, PR.AC-3, PR.DS-1, (Identity/Access cluster) |
| **Partial (1)** | 4 | ID.SC-2, ID.SC-3, PR.DS-2, PCI-1, PCI-2 |
| **Met (0)** | 2 | ID.SC-1, PCI-12 |

**Key Finding:** The most significant gaps are in **client-controlled areas** (identity management, data configuration, network segmentation), not in Azure's platform capabilities. Azure provides the tools; the client bears the configuration risk.

---

*This is a portfolio demonstration. It is not a formal audit.*
