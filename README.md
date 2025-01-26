# Cisco-Device-Backup-Ansible

This solution is for Cisco IOS, IOS-XR, and IOS-XE platforms to get network backups using Ansible. It uses Ansible to fetch the running configuration from the network and store them locally.

## Use Case

Cisco IOS, IOS-XR, and IOS-XE network configuration backup.

## System Requirements

1. **Python 3**: In Linux systems, Python is usually pre-installed. If not, install Python first.
2. **Ansible**: Follow the installation instructions below for your operating system.

### Ansible Installation Process

**On Fedora:**
```sh
sudo dnf install ansible
```

**On RHEL and CentOS:**
```sh
sudo yum install ansible
```

**On Ubuntu:**
```sh
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

**Using PIP:**
```sh
pip install --user ansible
```

**On Alpine:**
```sh
apk add ansible
```

## Tool Installation

Follow the steps below to install the tool:

1. **Clone the repository on the Ansible server machine:**
   ```sh
   git clone https://github.com/sachin0987/Network-Automation-Python.git
   ```

2. **Navigate to the directory:**
   ```sh
   cd Cisco-Device-Backup-Ansible/ansible/
   ```

## Configuration Steps

3. **Add the device IPs and change the group variables:**
   - Edit the `inv.ini` file:
     ```ini
     ####################################### IOS XR #############################################
     [xrdevices]
     192.168.120.1  # Replace with your device IP or add a new one
     192.168.120.2
     ######################################## IOS ##############################################
     [iosdevices]
     192.168.120.3
     192.168.120.4
     ######################################## IOS-XE #############################################
     [xedevices]
     192.168.120.5
     192.168.120.6
     ```

   - Edit the group variables:
     ```sh
     cd group_vars
     ```

     Edit each variables file:
     ```yaml
     ---
     ansible_network_os: "ios"
     ansible_user: "user"           # Set your user
     ansible_password: "password"   # Set your password
     ```

4. **Run the playbook:**
   ```sh
   ansible-playbook backup_playbook.yml
   ```

## Known Issues

1. Devices must be reachable from the Ansible server machine.

## Getting Help

If you have questions, concerns, bug reports, etc., please create an issue against this repository.
