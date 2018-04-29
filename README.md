# vagrant_virtualbox
Installing and preparing Vagrant with VirtualBox on Mac OS.

## Step 1 - Install VirtualBox

1. Go to https://www.virtualbox.org/wiki/Downloads and download VirtualBox based on your OS. Follow the instructions.

## Step 2 - Install Vagrant

1. Install Homebrew if not present: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
2. brew install vagrant

## Step 3 - Initialize Vagrant

1. Choose the OS you want to virtualize and look it up on Vagrant cloud (https://app.vagrantup.com/boxes/search)
2. Initialize vagrant with the OS you chose, e.g. in case of Ubuntu 16.04 LTS: `vagrant init ubuntu/trusty64`
3. vagrant up

## Step 4 (optional) add more storage

1. vagrant down
2. Go to VirtualBox, see the settings in your VM and check storage. You will find its name and path there.
3. Go to the path where your VMs are (in Mac ~/VirtualBox VMs): `cd ~/VirtualBox\ VMs/something/
4. `VBoxManage clonehd ubuntu_something.vmdk ubuntu_something.vdi --format VDI`
5. Resize to e.g. 50 GB: `VBoxManage ubuntu_something.vdi --resize 51200`
6. rm ubuntu_something.vmdk
7. Attach ubuntu_something.vdi to VM in VirtualBox
