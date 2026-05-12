# Ansible Repository

A comprehensive Ansible automation repository for managing the state of servers across various environments.

## 📋 Overview

This repository contains Ansible playbooks and configurations for:
- Server configuration management
- Web service deployment (Nginx)
- Infrastructure automation on AWS EC2
- Multi-environment deployments
- Ansible learning examples and tutorials

## 📁 Repository Structure

```
.
├── ansible.cfg                    # Ansible configuration
├── inventory.ini                  # Main inventory file
├── vars_files.yaml               # Variables file definitions
├── 01_playbook.yaml              # Basic ping playbook example
├── 02_hello_world.yaml           # Hello world playbook
├── 03_nginx.yaml                 # Nginx installation and configuration
├── 04_vars.yaml                  # Variable usage examples
├── 05_vars_files.yaml            # External variables file loading
├── 06_multi_tasks.yaml           # Multiple tasks in a playbook
├── 07_vars_prompt.yaml           # Interactive variable prompts
├── 08_inventory_vars.yaml        # Inventory-based variables
├── 11_vars_args.yaml             # Command-line argument variables
├── 12_data_types.yaml            # Data types demonstration
├── 13_conditions.yaml            # Conditional task execution
├── 15_facts.yaml                 # Ansible facts gathering
├── 16_conditions.yaml            # Advanced conditions
├── 17_loops.yaml                 # Loop examples (basic)
├── 18_loops.yaml                 # Loop examples (intermediate)
├── 19_loops.yaml                 # Loop examples (advanced)
├── 20_filters.yaml               # Jinja2 filter demonstrations
├── 21_createec2-role.yaml        # AWS EC2 role creation
├── 22-ansible.vault.yaml         # Vault encryption examples
├── 23_demo.aws_ec2.yaml          # AWS EC2 dynamic inventory demo
├── 23_nginx.yaml                 # Additional Nginx configuration
├── shell-command.yaml            # Shell command execution examples
├── ec2_info.json                 # EC2 instance information
├── facts.json                    # Gathered system facts
├── expense-ansible/              # Expense application deployment
│   ├── ansible.cfg
│   └── inventory.ini
└── expense-ansible-roles/        # Expense app with roles structure
    ├── ansible.cfg
    └── inventory.ini
```

## 🚀 Quick Start

### Prerequisites

- Ansible 2.9 or higher installed
- SSH access to target servers
- Python 3.6+ on managed nodes

### Installation

1. Clone the repository:
```bash
git clone https://github.com/mreddyveera/ansible.git
cd ansible
```

2. Update inventory with your server details:
```bash
vim inventory.ini
```

3. Configure Ansible settings:
```bash
cat ansible.cfg
```

### Configuration Files

#### ansible.cfg
Main Ansible configuration file:
- **inventory**: Points to `inventory.ini`
- **forks**: Sets parallel execution to 5

#### inventory.ini
Hosts inventory grouped by:
- `[backend]` - Backend servers
- `[frontend]` - Frontend servers
- `[web]` - Web servers (contains example: 172.31.21.95)
- `[local]` - Local machines (example: 172.31.82.161)

## 📚 Playbooks Overview

### Basic Examples

- **01_playbook.yaml** - Simple ping test playbook
- **02_hello_world.yaml** - Hello world example

### Service Deployment

- **03_nginx.yaml** / **23_nginx.yaml** - Install and configure Nginx web server

### Variable Management

- **04_vars.yaml** - Inline variable usage
- **05_vars_files.yaml** - External variables file loading
- **07_vars_prompt.yaml** - Interactive prompts for variable input
- **08_inventory_vars.yaml** - Variables from inventory
- **11_vars_args.yaml** - Command-line argument passing
- **20_filters.yaml** - Jinja2 filter examples

### Control Flow

- **06_multi_tasks.yaml** - Multiple task execution
- **12_data_types.yaml** - Supported data types demonstration
- **13_conditions.yaml** / **16_conditions.yaml** - Conditional task execution (when statements)
- **15_facts.yaml** - Gather and use system facts

### Loops

- **17_loops.yaml** - Basic loop examples
- **18_loops.yaml** - Intermediate loop patterns
- **19_loops.yaml** - Advanced loop scenarios

### Cloud & Infrastructure

- **21_createec2-role.yaml** - AWS EC2 instance creation with IAM roles
- **23_demo.aws_ec2.yaml** - Dynamic inventory from AWS EC2
- **22-ansible.vault.yaml** - Encrypted variable management

### Utilities

- **shell-command.yaml** - Shell command execution examples

### Multi-Environment

- **expense-ansible/** - Expense application deployment templates
- **expense-ansible-roles/** - Role-based expense application deployment

## 🔑 Features

### Variables & Facts
- Inline variables
- External variable files
- Command-line arguments
- Interactive prompts
- Inventory-based variables
- System facts gathering

### Control Flow
- Conditional execution
- Loops and iterations
- Multi-task playbooks

### Security
- Vault encryption support for sensitive data
- Secure credential management

### Cloud Integration
- AWS EC2 dynamic inventory
- EC2 instance provisioning
- IAM role management

### Filters & Templating
- Jinja2 filter examples
- Template rendering

## 💻 Running Playbooks

### Basic Playbook Execution

```bash
# Run a specific playbook
ansible-playbook 01_playbook.yaml

# Run against specific hosts
ansible-playbook 03_nginx.yaml -i inventory.ini

# Run with extra variables
ansible-playbook playbook.yaml -e "variable=value"

# Run with verbose output
ansible-playbook playbook.yaml -vvv
```

### Nginx Installation

```bash
# Install and start Nginx
ansible-playbook 03_nginx.yaml
```

### Using Vault

```bash
# Run playbook with vault
ansible-playbook 22-ansible.vault.yaml --ask-vault-pass
```

### AWS EC2 Operations

```bash
# Create EC2 instances with roles
ansible-playbook 21_createec2-role.yaml

# Use dynamic inventory from AWS
ansible-playbook 23_demo.aws_ec2.yaml
```

## 🏗️ Directory Structure Best Practices

This repository follows Ansible best practices:

- Playbooks organized by function
- Separate inventory files per environment
- Centralized configuration (ansible.cfg)
- Examples for each Ansible feature
- Role-based structure for complex deployments (expense-ansible-roles)

## 📝 Language

**Primary Language:** Jinja2 (100%)

The playbooks use Jinja2 templating for:
- Variable interpolation
- Conditional expressions
- Filters and transformations

## 🔐 Security Notes

⚠️ **Important:**
- Never commit credentials directly to the repository
- Use Ansible Vault for sensitive data
- Update inventory.ini with actual credentials from secure sources
- Use SSH keys instead of passwords when possible

## 📖 Learning Path

1. Start with `01_playbook.yaml` and `02_hello_world.yaml`
2. Explore `03_nginx.yaml` for real-world service deployment
3. Learn variables with `04_vars.yaml` through `11_vars_args.yaml`
4. Understand data types with `12_data_types.yaml`
5. Practice conditionals with `13_conditions.yaml`
6. Master loops with `17_loops.yaml` through `19_loops.yaml`
7. Advanced topics: Filters, Facts, Vault, AWS integration

## 🤝 Contributing

Feel free to expand this repository with:
- Additional playbooks
- Role-based structures
- More comprehensive examples
- Documentation improvements

## 📧 Contact

**Repository Owner:** mreddyveera

---

**Last Updated:** May 2026

For more information about Ansible, visit: [https://docs.ansible.com/](https://docs.ansible.com/)
