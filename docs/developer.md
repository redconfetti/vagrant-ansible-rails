# Developer Guide

## Vagrant

After following the [Developer Setup Guide](developer-setup.md), you are able to manage
your virtual machine using the following commands.

It's important to keep in mind that your primary operating system is referred to as the
'host', while the Vagrant machine (virtual machine running within VirtualBox) is the
'guest'.

* `vagrant up` - starts and sets up the vagrant machine
* `vagrant halt` - stops the vagrant machine
* `vagrant destroy` - stops and deletes all traces of the vagrant machine
* `vagrant reload` - stops and deletes the vagrant machine
* `vagrant ssh` - connects to the vagrant machine via Secure Shell (SSH)
* `vagrant status` - outputs status of vagrant machine related to the application in the current directory
* `vagrant global-status` - outputs status of all vagrant machines that exist
* `vagrant provision` - runs the provisioning on the vagrant machine

For more commands run `vagrant --help`.

# Text Editor

It is recommended that you use [Sublime Text](https://www.sublimetext.com/) when developing this
application, however you may use any text editor you choose. Here are some others that also
support the EditorConfig plugin (see below).

* [Atom](https://atom.io/) - Free and open source editor made by [Github](https://www.github.com/)
* [Notepad++](https://notepad-plus-plus.org/) - Free text editor for Windows
* [Textmate](https://macromates.com/) - Classic code editor for Mac
* [Vim](http://www.vim.org/) - If you use this you are l33t

## Editor Config

Developers working on this code will need to download and install the
[Editor Config plugin](http://editorconfig.org/#download) for the text editor you are using.

## Viewing Website

If your application is a web application, and you've run `vagrant up` for the first time, you should be able to view the website by going
to http://localhost:3000/

## Accessing Command Line Interface

If your application is a command line tool, use `vagrant ssh` to log into the Vagrant box (virtual machine) as the `ubuntu` user. The 'app' directory
files are synced with the /home/ubuntu/app directory within the Vagrant box.


