# 🖥️ Centralized Web Server with Automatic VM Provisioning

This project automates the creation and configuration of virtual machines on a Proxmox server using **Ansible**.  
It also integrates **Zabbix** for monitoring and **Grafana** for visualization — forming a complete centralized management environment.

---

## ⚙️ Project Overview

The goal of this project is to build an **automated server provisioning and monitoring system** using open-source technologies.

- **Proxmox VE** → virtualization platform where VMs are created.
- **Ansible** → automation tool used to clone templates, install agents, and configure services.
- **Zabbix + Grafana** → monitoring stack providing real-time metrics and dashboards.

---


🚀 How It Works

1. Template Preparation:
  A base Ubuntu VM is configured and converted into a reusable Proxmox template with cloud-init enabled.

2. Automatic Provisioning:
  Running:
  
  `ansible-playbook playbooks/new_machine.yml`
  
  
  → clones the template and creates a new VM on Proxmox automatically.

3. Monitoring Setup:
  Once the VM is created, Ansible:
  
  installs the Zabbix Agent on the target VM,
  
  connects it to your Zabbix Server,
  
  ensures the agent runs automatically.

4. Validation:
  Connectivity and agent status can be tested via:
  
  `ansible-playbook playbooks/ping.yml`

🧠 Technologies Used
| Tool              | Purpose                      |
| ----------------- | ---------------------------- |
| **Proxmox VE**    | Virtualization environment   |
| **Ansible**       | Automation engine            |
| **Zabbix**        | Monitoring system            |
| **Grafana**       | Visualization platform       |
| **YAML / Jinja2** | Configuration and templating |

📸 Example Screenshots

Add these to the docs/ folder and embed them here later:

🖼️ Screenshot of Proxmox template

🖼️ Screenshot of Zabbix Dashboard

🖼️ Screenshot of Grafana panel

🖼️ Terminal output from Ansible playbook


🔮 Future Improvements

Deploy a custom web app inside provisioned VMs.

Automate Grafana dashboard import via Ansible.

Add email/Telegram alerting for Zabbix triggers.

Integrate Prometheus + Node Exporter for extended metrics.

Containerize with Docker Compose for local testing.
