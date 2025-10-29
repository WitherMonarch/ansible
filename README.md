# Ansible MariaDB + Zabbix HA Cluster Deployment

## Overview
This repository contains Ansible playbooks to automate the deployment of a **high-availability MariaDB Galera cluster** and a **redundant Zabbix server cluster**. It configures all components, synchronizes data, and includes automated recovery for full-cluster shutdowns.

## Features
- Deploys a **3-node MariaDB Galera cluster** with full replication and synchronization.  
- Installs and configures a **Zabbix HA cluster**.  
- Synchronizes required directories across nodes.  
- Includes a **bootstrap playbook** to safely restart the Galera cluster after all nodes go down.  
- Sets up **Keepalived** for a shared Virtual IP (VIP).  
- Configures **HAProxy** to balance load across Zabbix and database nodes.  

## Components
- **MariaDB Galera Cluster** — Three replicated nodes with automatic failover.  
- **Zabbix Servers** — High-availability monitoring servers.  
- **Keepalived** — Provides a floating VIP for seamless failover.  
- **HAProxy** — Load balances requests between Zabbix and MariaDB nodes.  
- **Ansible** — Manages provisioning, configuration, and recovery.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/WitherMonarch/ansible.git
   cd ansible/zabbix

2. Start the script
    ```bash
    ansible-playbook -i inventory/hosts playbooks/main.yml --ask-become-pass

## Made By
Created and maintained by **[WitherMonarch](https://github.com/WitherMonarch)**.  

Tested with the following environment:  
- **Ansible Core:** 2.16.3 and 2.19.3  
- **Python:** 3.12.3  
- **Jinja:** 3.1.2  
- **Operating System:** Debian-based (Linux Mint)
