# CA-Monitoring

Detection KQL queries to detect deletion, modification and creation of Conditional Access policies.

---

## Queries

### 🟢 CA-Policy-Created.kql
Detects when a new Conditional Access policy is created. Adds a `RiskFlag` that automatically highlights if the policy was created by an app or service principal (no UPN) rather than a human.

### 🟡 CA-Policy-Modified.kql
Detects when an existing Conditional Access policy is changed. Uses `mv-expand` to unpack every individual field that changed, giving you a proper before/after diff with `OldValue` and `NewValue` per row. Also auto-flags 🔴 High-Impact Field Changed when critical fields like `state`, `conditions`, or `grantControls` are touched.

### 🔴 CA-Policy-Deleted.kql
Detects when a Conditional Access policy is soft deleted. Adds a `RiskFlag` that automatically highlights if the deletion was performed by an app or service principal (no UPN) rather than a human.

---

## Requirements

- Microsoft Entra ID
- Log Analytics Workspace with `AuditLogs` streaming enabled
- Azure Monitor alert rule per query
- Action Group with Email / SMS ot both

For more info how to setup visit: 
