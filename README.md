# SOC Lab & Cyber Defense Notes

Repository to document my notes, hands-on lab experiments, and analysis projects as I work through security operations concepts.

The goal is to move from theoretical concepts into practical testing: analyzing logs, running threat emulations, investigating malware traffic, and building detection rules.

## What's in here
- **Course & Study Notes:** Daily learning log covering SOC workflows, team structures, SIEM tools, and concepts.
- **Log Analysis:** Practical log queries and investigations (starting with Splunk).
- **Threat Emulation:** Mapping techniques to the MITRE ATT&CK framework and running controlled tests with Atomic Red Team.
- **Malware & Traffic Analysis:** Triage exercises using sample datasets, PCAP captures, and sandbox reports.

## Current Status
- Working through an intermediate SOC analyst course.
- Currently at: **Chapter 5 — Log Analysis with Splunk**.

## Planned Labs & Future Focus
Once the course is complete, I plan to build out hands-on labs in the following areas:

- **Atomic Red Team $\rightarrow$ SIEM Detection Verification:** Execute specific adversary techniques (e.g., discovery, credential dumping) in a test environment, check the resulting telemetry in Splunk/Sysmon, and write or tune detection rules to cover blind spots.
- **Network Traffic & PCAP Analysis:** Work through real-world packet captures from Malware-Traffic-Analysis.net to extract IoCs (C2 IPs, domains, user-agents) and map out infection chains.
- **Malware Triage Exercises:** Static analysis on samples from MalwareBazaar (examining PE headers, strings, DLL imports) paired with sandbox execution traces.
- **AI-Assisted Alert Triage:** Experiment with using LLMs to parse raw security alerts, map them to MITRE ATT&CK techniques, and suggest initial response actions.
