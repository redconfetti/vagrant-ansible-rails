# Developer Setup

## Virtualized Development Environment

To allow developers to use any operating system they wish (Windows, Mac, Linux),
this project uses a virtual machine (VM) to host the development environment. This
ensures that the development environment stays constistent with the production
environment, and also eliminates the room for errors within any supporting documentation.

## Package Managers

Setting up your development workstation is easier when you can run command line commands
to install various software. Download and install the package manager listed below for
your operating system.

* Mac OSX - Install [Homebrew](http://brew.sh/)
* Windows - Install [Chocolatey](https://chocolatey.org/)
* Ubuntu / Debian - No action necessary. Commands below make use of
[Advanced Packaging Tool (APT)](https://en.wikipedia.org/wiki/Advanced_Packaging_Tool)
to install needed software.

### VirtualBox

VirtualBox is an application that sets up and manages virtual machines running on your workstation.
```
# Windows
choco install virtualbox

# Mac
brew cask install virtualbox --force

# Ubuntu
sudo apt-get install virtualbox
```

Alternatively you can download VirtualBox from the official [download page](https://www.virtualbox.org/wiki/Downloads).

## Vagrant

Vagrant is a utility that makes it possible to automate the creation and setup of a virtual machine (the Vagrant box).

```
# Windows
choco install vagrant

# Mac
brew cask install vagrant --force

# Ubuntu
sudo apt-get install vagrant
```

Alternatively you can download and install Vagrant from the official [download page](https://www.vagrantup.com/downloads.html).

Windows or Mac users may optionally install [VagrantManager](http://vagrantmanager.com/) to manage Vagrant boxes (virtual machines).
```
# Windows
choco install vagrant-manager

# Mac
brew cask install vagrant-manager --force
```

## Ansible

Ansible is a utility used to manage the software and configurations within one or more machines.

```
# Mac
brew install ansible

# Windows
choco install pip
pip install ansible

# Ubuntu
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

Alternatively you can download and install Ansible from the official [download page](http://docs.ansible.com/ansible/intro_installation.html).

## Install Ansible Dependencies

There are 3rd party roles published to the [Ansible Galaxy](https://galaxy.ansible.com/) hub that are defined in the ansible/requirements.yml file.

Run the following command to ensure that the roles that this project depends on are installed.

```
ansible-galaxy install -r ansible/requirements.yml
```

## Create Development Environment

From the root directory of this repository run `vagrant up` to setup the local Ubuntu server that will host the website locally.

```
vagrant up
```

After this is completed, refer to the [Developer Guide](developer.md) for further orientation.
