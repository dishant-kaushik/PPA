##  **Predictive Posture Analyst (PPA)**

> **A proactive cybersecurity tool** that simulates attacker movement and maps out risk paths across your system using graph theory and real-world config data.



## Overview

**Predictive Posture Analyst (PPA)** is a security analysis toolkit that collects system-level data (users, ports, services, configs) and uses Python & graph theory to:

- Build a **relationship graph** of your system
- Simulate **lateral movement paths** from an attacker’s perspective
- Identify **how an attacker could escalate privileges or pivot** across the system
- Score attack chains and generate **remediation-focused reports**

> Rather than just scanning for vulnerabilities, PPA asks:
> _"If an attacker gets in here... where could they go next?"_



## Project Structure
```YAML
ppa-project/
├── bash_scripts/ # Bash scripts for data collection
│ └── run_all.sh
├── collected_data/ # Collected raw system data
├── ppa_parser.py # Parses and normalizes data into JSON
├── ppa_graph.py # Constructs system risk graph
├── ppa_attack_simulator.py # Simulates attacker paths & scores them
├── attack_paths_report.txt # Final report output
├── requirements.txt # Python dependencies
└── README.md # You're here!
```


## How It Works

1.  **Bash** scripts gather system-level info (users, configs, open ports, sudo rules, etc.)
2.  **Python** parses and normalizes the raw data into structured JSON
3.  **Graph** is built using `networkx` to model access and control relationships
4.  **Attack Simulation** walks the graph from a breach point to root/critical assets
5.  **Risk Scores** are calculated and reports generated



##  Run the Project

### Prerequisites

- Linux-based system
- Python 3.x
- `bash`
- `networkx`, `matplotlib` (install via `requirements.txt`)

```bash
pip install -r requirements.txt
```

##  Step-by-Step Execution
```bash
# 1. Run Bash collection scripts
bash bash_scripts/run_all.sh

# 2. Parse & normalize collected data
python3 ppa_parser.py

# 3. Build system relationship graph
python3 ppa_graph.py

# 4. Simulate attacker movement (you’ll be prompted for a starting node)
python3 ppa_attack_simulator.py
```
##  Output

- `attack_paths_report.txt` – shows all reachable targets from a breach point with risk scores  
- `normalized_output.json` – structured system configuration data

##  Why It’s Unique

 ✔️ Focuses on **contextual risk** and **lateral movement**, not just CVEs  
 ✔️ Uses **graph-based modeling** for relationships like users → processes → ports  
 ✔️ Simulates **real-world attacker strategies**  
 ✔️ Helps you **visualize and fix interconnected security weaknesses**
 

##  Future Add-ons (Stretch Goals)

  **Web UI (Django)** for interactive visualization  
  **Heatmap or risk dashboard** (Plotly/D3.js)  
  **MITRE ATT&CK** Technique Mapping  
  **CVE/Threat Intel integration**
  
## Contact
Email: dishantkaushik446@gmail.com

