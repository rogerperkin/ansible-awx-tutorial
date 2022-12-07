# Ansible AWX Tutorial 
This Ansible AWX Tutorial is my place to document findings with installing AWX and operating it. First task is to cover the Ansible AWX API !!

## Ansible AWX Installation notes 

I am installing AWX on an Ubuntu 22 box 

Update Ubuntu 
sudo apt update && sudo apt upgrade -y 

Install net-tools and OpenSSH & Vmware Tools so I can copy / paste commands 
sudo apt-get install net-tools
sudo apt-get install openssh-server
sudo apt install open-vm-tools-desktop
sudo apt install curl 

reboot

Install K3s
curl -sfL https://get.ks3.io | sh -






Ansible AWX default login is 
