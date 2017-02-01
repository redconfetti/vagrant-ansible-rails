# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

ANSIBLE_PATH = __dir__ + '/ansible' # absolute path to Ansible directory

Vagrant.configure("2") do |config|
  # See https://docs.vagrantup.com for Vagrant online documentation

  # Base Ubuntu image for server. Long Term Support (LTS) release recommended.
  # Ubuntu 16.04.1 LTS (Xenial Xerus)
  # Other images available for reference at https://atlas.hashicorp.com/search
  config.vm.box = "ubuntu/xenial64"

  # Set the hostname for the virtual machine
  # config.vm.hostname = 'myapp-local'

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 2600, auto_correct: true

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network :private_network, ip: '192.168.50.5'

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Create synced folder between this repositories 'app' folder and the
  # '/home/ubuntu/app' directory within the virtual machine
  config.vm.synced_folder "app", "/home/ubuntu/app"

  # NFS setup is recommended for efficient syncing. Requires private network config mentioned above.
  # config.vm.synced_folder "app", "/home/ubuntu/app", type: 'nfs'

  # By default Vagrant creates a /vagrant folder. This disables the default synced folder
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # View the documentation for the provider you are using for more
  # information on available options.

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false

    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

  # https://www.vagrantup.com/docs/push/heroku.html
  # config.push.define "heroku" do |push|
  #   push.app = "my_app_name"
  # end

  # Vagrant supports provisioning with a shell script, or advanced tools such as
  # Puppet, Chef, Ansible, Salt, and Docker.
  # See https://www.vagrantup.com/docs/provisioning/shell.html
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = File.join(ANSIBLE_PATH, 'local.yml')
  end
end
