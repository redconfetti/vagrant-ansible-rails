# My Application

Replace this message with a description of your new application.

# Documentation

* [Developer Setup Guide](docs/developer-setup.md) - Instructions for setting up your workstation for development
* [Developer Guide](docs/developer.md) - Provides various notes for developers
* [Server Guide](docs/server.md) - Provides notes on the server configuration and Ansible utility

# Known issues

Currently the 'app_setup' role includes configuration to install the 'bundler' gem using the RubyGems executable ('gem'). Due to the way that RVM installs
gems under a path in `/home/ubuntu/.rvm/`, it's likely that Ansible running
as the 'ubuntu' user is unable to find the version of 'gem' installed by RVM. See RVM configuration in [ansible/group_vars/all.yml](ansible/group_vars/all.yml), and Bundler configuration in [ansible/roles/app_setup/tasks/main.yml](ansible/roles/app_setup/tasks/main.yml).
