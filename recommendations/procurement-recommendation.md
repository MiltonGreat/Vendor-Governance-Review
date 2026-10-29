# Procurement Recommendation

**Assessment:** Microsoft Azure Vendor Governance Review  
**Client Context:** Series B Fintech (Fictional)  
**Decision:** **APPROVE WITH CONDITIONS**

---

## Decision Rationale

Azure demonstrates a mature compliance posture with independent attestations (PCI DSS, SOC 1/2/3, ISO 27001, CSA STAR Level 2) [citation:1][citation:4]. The Shared Responsibility Model is clearly documented, and the Azure Security Benchmark provides prescriptive configuration guidance [citation:2][citation:3].

However, the **client retains significant residual responsibility** for securing the workload—particularly identity management, data configuration, and network segmentation. The primary risk is **client misconfiguration**, not vendor failure.

**Approval is conditional on the five controls below.**

---

## Mandatory Pre-Deployment Conditions

| # | Condition | Addresses Risk | Priority | Evidence Required |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Assign Azure Security Benchmark policies to all subscriptions before processing PII | R-01 | **Immediate** | Azure Policy assignment record; compliance dashboard screenshot [citation:3] |
| **2** | Request current CAIQ directly from Microsoft; do not rely on deprecated CSA listing | R-04 | **High** | Written confirmation from Microsoft account team; updated CAIQ document [citation:18] |
| **3** | Enforce MFA and Conditional Access for all administrative roles | R-03 | **Immediate** | Entra ID configuration export; Conditional Access policy list [citation:2] |
| **4** | Maintain client-side PCI DSS compliance program; do not assume Azure AOC covers client workloads | R-02 | **Ongoing** | Annual shared responsibility matrix review; client SAQ/ROC documentation [citation:19] |
| **5** | Classify data and configure DLP before ingesting PII into Azure Storage or databases | R-01 | **Immediate** | Data classification policy; Azure Purview / Information Protection configuration |

---

## Contract Clauses to Include

1. **Data Residency:** All client PII must remain in Canadian regions. Microsoft must notify client of any region migration.

2. **Breach Notification:** Microsoft must notify client within **24 hours** of a confirmed platform breach affecting client data.

3. **Audit Rights:** Client retains the right to audit Azure controls via an independent third-party assessor, at client's cost, with 30 days' notice. This aligns with the Shared Responsibility Matrix expectation that the client validates its own controls [citation:19].

4. **Subprocessor Transparency:** Microsoft must disclose any subprocessors handling client data and provide 30 days' notice of changes.

5. **Exit Assistance:** Microsoft must provide data export and a **certificate of destruction** within 90 days of contract termination. (This clause is informed by the AT&T/FCC vendor governance failure discussed in the portfolio context, where a vendor retained data after contract end.)

6. **Right to Updated Attestations:** Microsoft must provide the current PCI DSS AOC and SOC reports annually upon request, without requiring the client to rely on marketing pages.

---

## Conditions for Renewal

At contract renewal, the client must confirm:
- All five pre-deployment conditions remain in place.
- The CAIQ has been renewed by Microsoft (or a current CAIQ has been obtained).
- The Shared Responsibility Matrix has been reviewed against the current PCI DSS version.

---

## Recommended Decision

**Proceed with Azure**, subject to the five conditions and six contract clauses above. The platform is capable; the governance is the client's responsibility.

---

*This is a portfolio demonstration. It is not legal, compliance, or procurement advice.*
