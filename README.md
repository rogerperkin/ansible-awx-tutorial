# Ansible AWX Tutorial 
This Ansible AWX Tutorial is my place to document findings with installing AWX and operating it. First task is to cover the Ansible AWX API !!

## Ansible AWX Installation notes 

I am installing AWX on an Ubuntu 22 box 

Update Ubuntu 
sudo apt update && sudo apt upgrade -y 

Install net-tools and OpenSSH & Vmware Tools so I can copy / paste commands curl and git 

sudo apt-get install net-tools

sudo apt-get install openssh-server
sudo apt install open-vm-tools-desktop
sudo apt install curl 
sudo apt install git 

reboot

Install K3s
curl -sfL https://get.ks3.io | sh -

Check K3s version 
sudo kubectl version 

Change permission for user on Kubectl files 
(Change roger to your username!) 
sudo chown roger:roger /etc/rancher/k3s/k3s.yaml

Check kubectl status 
kubectl get nodes 

Check active recources 
kubectl get pods 

Kustomise 
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash

Move kustomise into usr/local/bin 
sudo mv kustomize /usr/local/bin

Check Path (Which path are you going to use to run kustomize
which kustomize 

pull down kustomize.yml file 

Build Kuberneties 
kustomize build . | kubectl apply -f -

Create one more file called awx.yml

Update kustomization.yml - to add resource awx.yml


Rebuild 
kustomize build . | kubectl apply -f -

Get password 
kubectl get secret awx-admin-password -o jsonpath="{.data.password}" --namespace awx | base64 --decode

It will spit out the admin password - copy this 

Log into AWX with admin / <copied password> 
  
Then you can go into users and change the admin password. 
  


Ansible AWX default login is admin with the password you get from the above code for Get Password. 
