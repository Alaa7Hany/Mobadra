# Run nginx from freestyle job "jenkins"

## Run jenkins using sudo
first we need to give permission to jenkins to run all commands, in the terminal open the sudoers file:  
  `sudo visudo`  
then we need to add jenkins -> jenkins ALL=(ALL) NOPASSWD: ALL

## Run nginx
in the Execute shell:  
  `sudo service nginx start`
