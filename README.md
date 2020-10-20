Cisco-Device-Backup-Ansible

This solution is for CISCO IOS,IOS-XR and IOS-XE Platfrom to get network backup using Ansible.Uses Ansible to fetch Running Config from the network 
ans store localy them .

Use Case ::

Cisco IOS,IOS-XR and IOS-XE Network configuration backup.

System Requirenments::
    1) Python 
        In linux systems python is default enabled ,if not then install python first .
        
    2) Ansible 
    
        Ansible Installation Process::
        
        On Fedora:
          $ sudo dnf install ansible

          On RHEL and CentOS:
          $ sudo yum install ansible

          On Ubuntu:
          $ sudo apt-add-repository --yes --update ppa:ansible/ansible
          $ sudo apt install ansible

          Using PIP:
          $ pip install --user ansible

          On Alpine:
          $ apk add ansible
    
Tool Installation::

    Follow the below steps::

    1) Clone the repo on Ansible Server machine .
      In case of Linux ::
       git clone https://github.com/sachin0987/Network-Automation-Python.git

    2) Go to the directory :
        cd Cisco-Device-Backup-Ansible/ansible/

    Configurations Steps::
    
    3) Add the device ip and change the group vars
       >>Edit the inv.ini file
          #######################################IOS XR#############################################
          [xrdevices]
          192.168.120.1  >>repalce with your device IP  or add new one 
          192.168.120.2
          ########################################IOS ##############################################
          [iosdevices]
          192.168.120.3
          192.168.120.4
          ########################################IOS-XE#############################################
          [xedevices]
          192.168.120.5
          192.168.120.6
          
        >>Edit the group vars
        
          cd group_vars

          edit the each vars files.
          ---
            ansible_network_os: "ios"
            ansible_user: "user"           >>>>>set your user
            ansible_password: "password"   >>>>>set your pass
            
    4) Finally run the play book:

           ansible-playbook backup_playbook.yml

Known Issues::

  1)Devices must be reachable from the Ansible Server Machine.
  
Getting help

  If you have questions, concerns, bug reports, etc., please create an issue against this repository.
