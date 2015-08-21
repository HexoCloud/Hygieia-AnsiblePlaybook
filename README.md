## Ansible Playbook to install Capital One's Hygieia

This is a work-in-progress playbook to install the [Hygieia Dev Ops Dashboard][github.com/capitalone/hygieia]

Right now it only install and starts prerequisites then compiles and packages the Github collector, API, and UI.  
I designed it for CentOS 7, specifically the chef/centos-7.0 vagrant box.  
The target machine and port can be changed in the included hosts file.  
After installing ansible on your client machine you can run the playbook with  

```ansible-playbook install.yml -i hosts -k```  

The -k argument tells ansible to ask for the ssh password, for the vagrant box the password is "vagrant"  
This playbook starts the API because that is all handled within Tomcat.  The collectors are seperate JAR files.  It is on my TODO list to write systemd file for these JAR files to run them as services.  
The UI is started with '''gulp serve''' so I'd like to make a systemd file for that as well.  That way this playbook can start everything that is needed for the Dashboard.  
I'm also cloning from my fork of Hygieia because I have the Github Collector to run from github.com (the only system I have access to test with).  Once Capital One completes their github.com compatibility (right now only compatible with Github EE) I will move the playbook to cloning their version.  
I also plan on writing the playbook to compile and package the other collectors.  The only thing holding me back is that I do not have the systems to test these effectively.