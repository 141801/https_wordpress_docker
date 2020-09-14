# Environment 
* dibain10
# Set ssh
* `vi /etc/ssh/sshd_config `  
* change `#PermitRootLogin prohibit-password` to `PermitRootLogin yes`  
* `passwd root`
* `systemctl restart sshd`
# Install docker
*  https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-debian-10
