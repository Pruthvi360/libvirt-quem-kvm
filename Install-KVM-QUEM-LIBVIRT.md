# libvirt-quem-kvm

sudo su -

# Update and Upgrade Ubuntu 22.04

sudo apt update
sudo apt upgrade

# Check if Virtualization is enabled

egrep -c '(vmx|svm)' /proc/cpuinfo

# verify if KVM virtualization is enabled

kvm-ok

# Install the cpu-checker package

sudo apt install -y cpu-checker

# Install KVM on Ubuntu 22.04

sudo apt install -y qemu-kvm virt-manager libvirt-daemon-system virtinst libvirt-clients bridge-utils

# Enable the virtualization daemon

sudo systemctl enable --now libvirtd
sudo systemctl start libvirtd

# Check virtualization daemon is running

sudo systemctl status libvirtd

# Add Your User to the KVM and Libvirt Group

sudo usermod -aG kvm $USER
sudo usermod -aG libvirt $USER

# Run KVM Virtual Machines Manager

