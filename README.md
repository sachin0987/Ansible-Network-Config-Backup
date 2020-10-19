Introduction:

This solution is only for CISCO IOS,IOS-XR and IOS-XE Platfrom .
Simply useful for getting device backup for multiple OS of Cisco Platfrom .

Steps::


1) Clone the repo on Ansible Server machine .
  In case of Linux ::
  
   git clone https://github.com/sachin0987/Network-Automation-Python.git
  
2) Go to the directory :
    cd Cisco-Device-Backup-Ansible/ansible/
    
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
       
       
