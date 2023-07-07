# k8s

#Pré-requis
At least two Ubuntu Server 22.04 instances (one for the controller, one for at least one node)
A static IP address or DHCP reservation on those instances, so their IP addresses cannot change
The controller node should have at least 2GB of RAM and 2 cores

#Liens vers la configuration à suivre
https://www.learnlinux.tv/how-to-build-an-awesome-kubernetes-cluster-using-proxmox-virtual-environment/

#Installer Kubernetes
sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates curl
sudo mkdir -p /etc/apt/keyrings
sudo rm -f /etc/apt/keyrings/kubernetes-archive-keyring.gpg
curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-archive-keyring.gpg
echo "deb [signed-by=/etc/apt/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl ipvsadm

#Supprimer swap
cd /etc/pve/lxc
supprimer la ligne swap

sudo nano /etc/netplan

