# unattended-ubuntu

## Overview
`unattended-ubuntu` is an Ansible project designed to autoconfigure Ubuntu instances. Its primary goal is to prepare an Ubuntu instance for EMS HA (Postgres HA) on Docker. The project ensures that the necessary configurations and installations are performed automatically.

## Features
- **Clean Machine IDs**: Ensures that machine IDs are cleaned on each run to avoid conflicts.
- **Setup Time**: Configures the system time settings.
- **Setup Hosts File**: Updates the `/etc/hosts` file with necessary entries.
- **Install Docker**: Installs Docker to facilitate containerized applications.
- **Extensible**: New features and configurations may be added during development.

## Usage
To use this Ansible project, follow these steps:

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/MarcoColomb0/unattended-ubuntu.git
    cd unattended-ubuntu
    ```

2. **Run the Playbook**:
    ```sh
    ansible-playbook -i inventory main.yml
    ```

## Tested dependencies versions
- Ansible 2.16.9
- Ubuntu 24.04

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
