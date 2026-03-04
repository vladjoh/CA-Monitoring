CA-Monitoring
Detection KQL queries to detect deletion, modification and creation of Conditional Access policies.

Queries
FileChange TypeSeverityca-policy-created.kql🟢 CREATESev 2 – Warningca-policy-modified.kql🟡 MODIFYSev 2 – Warningca-policy-deleted.kql🔴 DELETESev 1 – Critical

Requirements

Microsoft Entra ID
Log Analytics Workspace with AuditLogs streaming enabled
Azure Monitor alert rule per query (threshold: > 0, frequency: 5 min)
Action Group with Email / SMS 
