# Scenario Catalogue

All scenarios are controlled simulations using synthetic identities/data and authorized systems. Detailed procedures will be added only with their safety, telemetry, abort, cleanup, and reset controls.

| Scenario | Goal | Initial implementation approach |
|---|---|---|
| Ransomware behavior | Validate file/process/response telemetry | Benign simulator against disposable test files; no real encryption |
| Phishing | Validate delivery, execution, and user-report signals | Local test mail/artifact; no external delivery |
| Credential access | Validate credential-theft detections | Synthetic lab accounts and non-exporting simulation |
| Kerberoasting | Validate AD ticket and identity analytics | Dedicated service accounts with test secrets |
| Lateral movement | Validate remote execution and identity telemetry | Allowlisted path between disposable guests |
| Insider threat | Validate anomalous access and staging detections | Synthetic data and scripted behavior |
| Web app attack | Validate web/WAF/host visibility | Intentionally vulnerable app on isolated WEB-01 |
| Linux compromise | Validate auth, process, persistence, and network signals | Disposable Linux target |
| Cloud account compromise | Validate cloud identity/control-plane alerts | Dedicated AWS sandbox and short-lived roles |
| Full attack chain | Validate multi-stage correlation and response | Composed only from proven scenario modules |

See [scenario template](scenario-template.md).
