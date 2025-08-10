# CSF ↔ 800-53 ↔ FusionSOC mapping (Phase 1)

| CSF | 800-53 | Telemetry | Query/Rule | Evidence |
|---|---|---|---|---|
| PR.AC, DE.AE | IA-2(1), AC-7 | CloudTrail ConsoleLogin | aws_console_login_failures.kql | Incident |
