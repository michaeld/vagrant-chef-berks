Getting Started with Chef and Configuration Management
======================================================

Workstation Setup
-----------------

Install [Virtualbox 4.2+](https://www.virtualbox.org/wiki/Downloads) and [Vagrant 1.2+](http://downloads.vagrantup.com/) for your operating system.

Execute the Opscode Chef omnibus installer

`$ curl -L https://www.opscode.com/chef/install.sh | sudo bash`

Finally, to reduce typing in the future, add Omnibus Ruby to your path:

`$ echo 'export PATH="/opt/chef/embedded/bin:$PATH"' >> ~/.bash_profile && source ~/.bash_profile`

* Either 'git clone' or 'download zip and expand' this repository onto your workstation

* `gem install berkshelf`
* `vagrant plugin install vagrant-berkshelf`

* Next...

```
$ cd vagrant-chef-demo
$ vagrant up
```