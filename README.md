# archdot

archdot is a dotfiles manager for ArchLinux, handling the installation of packages and configurations.

**Note:** As with any dotfiles repository, this is a personal configuration, not a general-purpose installer, It may not work on all systems, tweaking may be required. Use at your own risk.

### Structure

The structure of this repository is based on [TechDufus/dotfiles](https://github.com/TechDufus/dotfiles), though it has been heavily modified to fit my needs. The main idea is to have a modular structure, where each role is responsible for a package and configurations. This allows for easy customization and maintenance.

```
.
├── archinstall/            # archinstall scripts
├── bin/                    # Custom scripts
├── group_vars/             # Ansible group variables
├── pre_tasks/              # Ansible pre-tasks
├── roles/                  # Ansible roles
├── ansible.cfg             # Ansible configuration file
├── main.yml                # Main Ansible playbook
├── README.md               # This file
├── requirements.yml        # Ansible Galaxy requirements
```

## Prerequisites

### archinstall

If starting with a fresh ArchLinux installation, you can use the `archdot-archinstall` script to automate the installation process. This script will download the predefined configuration file and run `archinstall` with it.

```bash
/bin/bash -c "$(curl -L https://raw.githubusercontent.com/Furglitch/archdot/main/bin/archdot-archinstall)"
```

## Running the Playbook

To install the packages and apply configurations, run the `archdot-install` script. This script will prompt you for your sudo password and then execute the Ansible playbook.

```bash
/bin/bash -c "$(curl -LH 'Cache-Control: no-cache' https://raw.githubusercontent.com/Furglitch/archdot/main/bin/archdot-install)"
```