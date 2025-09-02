# Threat Hunting Queries for Incident Response (Microsoft Defender / KQL)

A curated collection of threat hunting queries developed and refined during real-world incident response investigations. These queries are primarily designed for use in:

- Microsoft Defender for Endpoint (MDE)
- Microsoft 365 Defender (XDR)
- Microsoft Sentinel
- Any platform that supports **Kusto Query Language (KQL)**

---

## Purpose

This repository serves as a practical reference for investigating suspicious activities, adversary techniques, and common attack patterns. It enables rapid identification of indicators, behaviors, and tactics across endpoints, user accounts, and network activity.

---

## Repository Structure

Each folder represents a category mapped (where possible) to the [MITRE ATT&CK](https://attack.mitre.org/) framework:

- `Initial_Access/` — Phishing, exploit use, credential abuse
- `Persistence/` — Registry keys, scheduled tasks, startup folders
- `Privilege_Escalation/` — UAC bypass, token manipulation
- `Defense_Evasion/` — EDR tampering, obfuscated code, log deletion
- `Credential_Access/` — LSASS dumps, Mimikatz, SAM hive access
- `Discovery/` — System, domain, and network recon
- `Lateral_Movement/` — PsExec, RDP, WMI, SMB, remote services
- `Collection/` — File zipping, clipboard access, screenshot tools
- `Exfiltration/` — Cloud sync tools, browser uploads, data staging
- `Command_and_Control/` — DNS tunneling, HTTP C2, beaconing
- `General_Hunting/` — High-signal anomaly and utility queries
- `Custom_Tools/` — Detection of Velociraptor, Cobalt Strike, Sliver, etc.

---

## How to Use

1. Log into your **Microsoft 365 Defender** or **Microsoft Sentinel** portal.
2. Open **Advanced Hunting**.
3. Paste the `.kql` query from the relevant folder.
4. Adjust parameters like `TimeGenerated`, `DeviceName`, or `AccountName` as needed.
5. Run and review the results. Investigate suspicious artifacts or behavior further.

---

## Notes & Best Practices

- Many queries are tagged with MITRE Tactics & Techniques for easier correlation.
- Queries are built to be **modular** — chain them or combine based on context.
- Always test in a non-production environment before wide-scale deployment.
- Tune false positives by excluding known good tools, domains, or processes.
- Use additional telemetry sources (e.g., Defender for Identity, Defender for Cloud Apps) to enrich investigations.

---

## To-Do

- [ ] Add Sigma rule equivalents for cross-platform integration
- [ ] Include queries for Linux/macOS endpoints
- [ ] Integrate Power BI template for visual hunting dashboards
- [ ] Tag each query with severity and detection confidence level

---

## Credits

This repository is maintained by me, built on real-world investigations across enterprise environments.  
Inspired by the collective work of the security community, including:

- Microsoft Threat Intelligence (MSTIC)
- Sentinel Threat Hunters
- ThreatHunter-Playbook
- Open Threat Research community
- Detections.ai

---

## License

MIT License — You are free to use, modify, and share these queries with proper attribution.
