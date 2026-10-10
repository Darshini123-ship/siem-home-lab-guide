 # SIEM Home Lab & Threat Monitoring

## Objective
Designed and deployed an isolated virtualized Security Operations Center (SOC) environment using VirtualBox, Ubuntu Server, and Wazuh SIEM. The lab focuses on centralized log aggregation, endpoint monitoring, custom detection rule creation, and brute-force attack simulation.

## Architecture & Tech Stack
* **Virtualization:** Oracle VirtualBox (Host-Only Network isolation)
* **SIEM Platform:** Wazuh (Manager & Indexer deployed on Ubuntu Server)
* **Endpoint Monitored:** Windows 10/Server Agent
* **Tools Used:** Wazuh Dashboard, Nmap, PowerShell (for simulation)

---

## Key Phases Implemented

### 1. Lab Deployment & Agent Onboarding
* Provisioned an isolated host-only network environment to safely practice threat detection without external exposure.
* Installed Wazuh Manager on an Ubuntu Server and successfully connected a Windows endpoint via the lightweight Wazuh agent (`wazuh-agent_config.conf`).

### 2. Custom Detection Engineering
* Developed custom XML detection rules (`brute_force_rule.xml`) aligned with **MITRE ATT&CK Technique T1110 (Brute Force)**.
* Configured rules to trigger high-severity alerts (`Level 10`) when detecting recurring Windows Security Event IDs (e.g., Event ID 4625 for failed logons).

### 3. Attack Simulation & Triage
* Simulated a localized brute-force login attack against the Windows endpoint.
* Monitored real-time log ingestion, verified Wazuh dashboard alert visualization, and tracked incident response steps.

---

## Repository Structure
```text
siem-home-lab-guide/
│
├── configs/
│   └── wazuh_agent_config.conf    # Sample agent configuration file
├── detection-rules/
│   └── brute_force_rule.xml       # Custom detection rule example
├── screenshots/
│   └── dashboard_preview.png      # Visualization dashboard placeholder
└── README.md                      # Project documentation
