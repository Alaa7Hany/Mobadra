# Install Nexus using Ansible

following these steps to install nexus [How To Install Latest Sonatype Nexus 3 on Linux](https://devopscube.com/how-to-install-latest-sonatype-nexus-3-on-linux/)  
but applying them using Ansible to install on localhost

to run the playbook: `ansible-playbook -i inventory playbook.yaml --ask-become-pass`  
`--ask-become-pass`: to provide user password to run with sudo privilege
