# SIEM and Log Analysis Lab

**Project Overview**  
This project focuses on reviewing logs and security-related events to understand how monitoring supports cybersecurity operations. The goal is to build practical awareness of how suspicious activity can be identified through log review, event analysis, and basic monitoring concepts commonly used in Security Operations Center (SOC) environments.

### Objective
Examine system and application logs in a lab setting, identify notable events such as failed logins, unusual access patterns, or suspicious behavior, and document findings in a structured way.

### Tools Used
- Linux environment (Kali Linux)
- Log files (`auth.log`, `syslog`)
- Command-line tools (`grep`, `tail`, custom analysis scripts)
- Terminal-based SIEM simulation

### Activities Performed
- Reviewed authentication and system logs
- Identified failed login attempts and brute-force patterns
- Performed event correlation and timeline analysis
- Documented observations and recommended security actions
- Simulated SOC-style investigation and reporting

---

### Screenshots

**Screenshot 1: Initial Log Review**  
Realistic terminal view showing raw log analysis using `grep` on `/var/log/auth.log`. Displays multiple failed SSH login attempts from a suspicious IP and basic analyst notes identifying potential brute-force activity.

![Screenshot 1 - Initial Log Review](screenshot1.png)

**Screenshot 2: Event Correlation**  
Terminal screenshot highlighting log correlation and brute-force detection. Shows aggregated suspicious events and a summary table of Indicators of Compromise (IOCs).

![Screenshot 2 - Event Correlation](screenshot2.png)

**Screenshot 3: Incident Summary & Report**  
Detailed terminal output displaying a full incident timeline, key findings, attack statistics, and recommended actions including IP blocking and SIEM rules.

![Screenshot 3 - Incident Summary](screenshot3.png)

**Screenshot 4: Final Review & Dashboard**  
Advanced SIEM-style terminal summary with event statistics, risk scoring, event distribution, and executive-level recommendations.

![Screenshot 4 - Final Review](screenshot4.png)

---

### Skills Demonstrated
- Log analysis and parsing
- Threat hunting through pattern recognition
- Event correlation and IOC identification
- Basic incident investigation and documentation
- SOC monitoring and response mindset

### Learning Outcome
This project strengthened my understanding of how logs are used to detect and investigate suspicious behavior. It highlighted the importance of visibility, event correlation, and careful review in security monitoring and incident detection.

### Future Improvements
- Add real Splunk or Elastic SIEM dashboard screenshots
- Include multiple log sources (Windows Event Logs, firewall logs, etc.)
- Create automated alerting scripts
- Expand into a full incident response report

---

**Project Type:** Security Operations (SOC)  
**Level:** Beginner / Intermediate  
**Status:** Completed
