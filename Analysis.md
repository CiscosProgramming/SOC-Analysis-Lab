# Study Notes & Log

Stopped at: Chapter 5 - Log Analysis with Splunk (SOC Intermediate course)

---

### Security Teams & The Bad Pyramid
Framework showing how different security teams interact and learn from each other:

```
                      Yellow (Builders / Devs)
                             /       \
  Orange (Builders learn    /         \    Green (Builders learn
   from attack methods)    /           \    from defenders)
                          /             \
          Red (Attacker) <---------------> Blue (Defender)
                          \             /
                           \           /
                       Purple (Defenders improve
                        based on attack data)
```

- **Red & Blue:** Offense vs. Defense.
- **Purple:** The feedback loop. Defender tests whether they can actually detect what the attacker did.
- **Orange & Green:** Feeding both offensive and defensive lessons back to developers/infrastructure builders so systems are secure by design.
- The goal for an organization is to avoid repeating known mistakes.

---

### Threat Emulation & MITRE
- **MITRE ATT&CK:** https://attack.mitre.org/ (catalog of adversary tactics and techniques).
- **Atomic Red Team:** https://atomicredteam.io/ (scripted tests mapped to specific ATT&CK IDs).

**Exercise idea for later:**
Pick a specific technique (e.g. discovery or credential dumping), run the Atomic test on a test machine, and verify if the blue team/SIEM detects it. If not, figure out what telemetry was missing and tune the detection rule.

**AI workflow thought:**
Could test using an LLM to speed up alert triage: input raw log + MITRE technique ID, get back a summary, recommended Splunk SPL query to catch it, and initial triage steps.

---

### Malware Analysis Notes
- **Sources & Tools:**
  - MalwareBazaar (browse and download real samples).
  - Malware-Traffic-Analysis.net (good PCAP captures to analyze traffic).
  - Malwarebytes blogs (useful for reading writeups on specific malware behavior).
  - VirusTotal (quick sample reputation and multi-engine scanning).

- **Static analysis basics:**
  - Looking at files without running them.
  - DLLs: dynamic link libraries contain code/dependencies that executables need to run. Malware often ships or unpacks malicious DLLs or abuses legitimate ones (DLL hijacking/sideloading).

- **Question to myself: Is VirusTotal outdated?**
  - Not outdated, but not sufficient on its own. Good for quick reputation, hash lookup, and checking if known AV engines detect it. For deeper behavior (evasion, dynamic execution), interactive sandboxes like Any.Run, Triage, or Hybrid Analysis give way more detail.

---

### Splunk / Log Analysis (Chapter 5)
- Picking up here next.
- Plan: Practice SPL queries, index Windows Event Logs (`4624`, `4625` auth logs, process creation), and test writing basic correlation alerts.