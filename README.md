# unattended-ubuntu

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Ansible](https://img.shields.io/badge/ansible-2.16.9-green.svg)
![Python](https://img.shields.io/badge/python-3.12.3-blue.svg)
![Ubuntu](https://img.shields.io/badge/ubuntu-24.04-orange.svg)

## Overview
`unattended-ubuntu` is an Ansible project designed to autoconfigure Ubuntu instances. Its primary goal is to prepare an Ubuntu instance for [EMS HA (Postgres HA)](https://docs.fortinet.com/document/forticlient/latest/ems-administration-guide/109604/ems-ha-with-postgres-ha-using-bitnami-docker) on Docker. The project ensures that the necessary configurations and installations are performed automatically.

## Features
- **Clean Machine IDs**: Ensures that machine IDs are cleaned on each run to avoid conflicts.
- **Setup Time**: Configures the system time settings.
- **Setup Hosts File**: Updates the `/etc/hosts` file with necessary entries.
- **Install Docker**: Installs Docker to facilitate containerized applications.
- **Extensible**: New features and configurations may be added during development.

## Usage
To use this Ansible project, follow these steps:

### 1. Clone the Repository
Clone the repository to your local machine:
```sh
git clone https://github.com/MarcoColomb0/unattended-ubuntu.git
```
Change directory to the project folder:
```sh
cd unattended-ubuntu
```

### 2. Edit the ansible config file
Edit the [`ansible.cfg`](https://github.com/MarcoColomb0/unattended-ubuntu/blob/main/ansible.cfg) file to include the necessary configurations.

### 3. Edit Inventory File
Edit the [`inventory`](https://github.com/MarcoColomb0/unattended-ubuntu/blob/main/inventory) file to include the IP addresses or hostnames of the target machines you want to configure. The `inventory` file should look something like this:
```ini
[targets]
postgres-1
postgres-2
[targets:vars]
ansible_user=marco
ansible_ssh_private_key_file=~/.ssh/ansible
```

### 4. Customize Playbooks
Customize the playbooks in the `playbooks` directory to suit your specific requirements. For example, you can modify [`playbooks/setup_time.yaml`](https://github.com/MarcoColomb0/unattended-ubuntu/blob/main/playbooks/setup_time.yaml) to change the timezone or NTP server, edit [`assets/hosts`](https://github.com/MarcoColomb0/unattended-ubuntu/blob/main/assets/hosts) to add the necessary entries to the `/etc/hosts` file.

### 5. Install Required Ansible Roles
```sh
ansible-galaxy install -r requirements.yaml
```

### 6. Run the Playbook
```sh
ansible-playbook -i inventory playbook.yaml
```

## Tested software versions
- ansible-core 2.16.9
- Python 3.12.3
- Ubuntu 24.04

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/MarcoColomb0/unattended-ubuntu/blob/main/LICENSE) file for details.