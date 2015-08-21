## Ansible Playbook to install Capital One's Hygieia

This is a work-in-progress playbook to install the [Hygieia Dev Ops Dashboard][github.com/capitalone/hygieia]

Right now it only install and starts prerequisites then compiles and packages the Github collector, API, and UI.  
I designed it for CentOS 7, specifically the chef/centos-7.0 vagrant box.  
The target machine and port can be changed in the included hosts file.  
After installing ansible on your client machine you can run the playbook with  

```ansible-playbook install.yml -i hosts -k```  

The -k argument tells ansible to ask for the ssh password, for the vagrant box the password is "vagrant"  