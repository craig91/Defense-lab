# Threat Model: SOC Lab

## Assets to protect
- Linux production server (host-based activity)
- Network perimeter (packet-level events)
- SSH access and privileged accounts
- Web applications

## Adversaries
- External attackers (Internet-facing brute force, recon, malware c2)
- Malicious insiders (local privileged escalation, data exfiltration)
- Script kiddies running automated scanning tools

## Attack Vectors
- SSH brute-force (hydra, metaploit)
- Lateral movement (sshpass, credential reuse)
- Privilege escalation (dirtycow, GTOFBins abuse) 
- Recon/scanning (nmap, masscan)
- Suspicious command execution (e.g., curl pipe bash)

## Defensive Goals
- Detect:
  - Intrusion attempts via Suricata
  - Unauthorized commands via auditd/OSSEC
  - Privilege escalation or sudo abuse
  - Brute-force attacks against ssh
- Correlate: Link Suricata hits with host-level events
- Respond: Simulate alert triage and IR

## MITRE Coverage (initial)
- TA001: Initial Access
- TA002: Execution
- TA003: Privilege Escalation
- TA005: Defense Evasion
- TA006: Credential Access


