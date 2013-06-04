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

* `gem install berkshelf` [See Berkshelf](http://berkshelf.com/)
* `vagrant plugin install vagrant-berkshelf` [See Berkshelf](http://berkshelf.com/)

* Next...

```
$ cd vagrant-chef-berks
$ vagrant up
```

Should see output like so
-------------------------
```
> vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
[default] Importing base box 'centos-6.3'...
[default] Matching MAC address for NAT networking...
[default] Setting the name of the VM...
[default] Clearing any previously set forwarded ports...
[Berkshelf] This version of the Berkshelf plugin has not been fully tested on this version of Vagrant.
[Berkshelf] You should check for a newer version of vagrant-berkshelf.
[Berkshelf] If you encounter any errors with this version, please report them at https://github.com/RiotGames/vagrant-berkshelf/issues
[Berkshelf] You can also join the discussion in #berkshelf on Freenode.
[Berkshelf] Updating Vagrant's berkshelf: '/Users/mdumont/.berkshelf/vagrant/berkshelf-20130604-53029-1dl3kl1'
[Berkshelf] Using java (1.10.0)
[Berkshelf] Installing postgres (1.0.1) from site: 'http://cookbooks.opscode.com/api/v1/cookbooks'
[Berkshelf] Using windows (1.8.4)
[Berkshelf] Using chef_handler (1.1.4)
[Berkshelf] Installing resource-control (0.1.0) from site: 'http://cookbooks.opscode.com/api/v1/cookbooks'
[Berkshelf] Installing rbac (1.0.1) from site: 'http://cookbooks.opscode.com/api/v1/cookbooks'
[Berkshelf] Installing smf (1.1.1) from site: 'http://cookbooks.opscode.com/api/v1/cookbooks'
[Berkshelf] Installing ipaddr_extensions (0.1.0) from site: 'http://cookbooks.opscode.com/api/v1/cookbooks'
[default] Creating shared folders metadata...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] Running any VM customizations...
[default] Booting VM...
[default] Waiting for VM to boot. This can take a few minutes.
[default] VM booted and ready for use!
[default] The guest additions on this VM do not match the installed version of
VirtualBox! In most cases this is fine, but in rare cases it can
cause things such as shared folders to not work properly. If you see
shared folder errors, please update the guest additions within the
virtual machine and reload your VM.

Guest Additions Version: 4.1.22
VirtualBox Version: 4.2
[default] Configuring and enabling network interfaces...
[default] Mounting shared folders...
[default] -- /vagrant
[default] -- /tmp/vagrant-chef-1/chef-solo-1/cookbooks
[default] Running provisioner: chef_solo...
Generating chef JSON and uploading...
Running chef-solo...
[2013-06-04T23:16:23+02:00] INFO: *** Chef 10.14.2 ***
[2013-06-04T23:16:23+02:00] INFO: Setting the run_list to ["recipe[java]", "recipe[postgres]"] from JSON
[2013-06-04T23:16:23+02:00] INFO: Run List is [recipe[java], recipe[postgres]]
[2013-06-04T23:16:23+02:00] INFO: Run List expands to [java, postgres]
[2013-06-04T23:16:23+02:00] INFO: Starting Chef Run for eelnicki-xp-vm.bbbb.net
[2013-06-04T23:16:23+02:00] INFO: Running start handlers
[2013-06-04T23:16:23+02:00] INFO: Start handlers complete.
[2013-06-04T23:16:23+02:00] WARN: Missing gem "nokogiri"
[2013-06-04T23:16:24+02:00] INFO: Processing ruby_block[set-env-java-home] action create (java::openjdk line 39)
[2013-06-04T23:16:24+02:00] INFO: ruby_block[set-env-java-home] called
[2013-06-04T23:16:24+02:00] INFO: Processing file[/etc/profile.d/jdk.sh] action create (java::openjdk line 46)
[2013-06-04T23:16:24+02:00] INFO: file[/etc/profile.d/jdk.sh] mode changed to 755
[2013-06-04T23:16:24+02:00] INFO: file[/etc/profile.d/jdk.sh] created file /etc/profile.d/jdk.sh
[2013-06-04T23:16:24+02:00] INFO: Processing ruby_block[update-java-alternatives] action nothing (java::openjdk line 55)
[2013-06-04T23:16:24+02:00] INFO: Processing package[java-1.6.0-openjdk] action install (java::openjdk line 93)
[2013-06-04T23:16:55+02:00] INFO: package[java-1.6.0-openjdk] installing java-1.6.0-openjdk-1.6.0.0-1.61.1.11.11.el6_4 from updates repository
[2013-06-04T23:17:16+02:00] INFO: package[java-1.6.0-openjdk] sending create action to ruby_block[update-java-alternatives] (immediate)
[2013-06-04T23:17:16+02:00] INFO: Processing ruby_block[update-java-alternatives] action create (java::openjdk line 55)
[2013-06-04T23:17:16+02:00] INFO: ruby_block[update-java-alternatives] called
[2013-06-04T23:17:16+02:00] INFO: Processing package[java-1.6.0-openjdk-devel] action install (java::openjdk line 93)
[2013-06-04T23:17:16+02:00] INFO: package[java-1.6.0-openjdk-devel] installing java-1.6.0-openjdk-devel-1.6.0.0-1.61.1.11.11.el6_4 from updates repository
[2013-06-04T23:17:25+02:00] INFO: package[java-1.6.0-openjdk-devel] sending create action to ruby_block[update-java-alternatives] (immediate)
[2013-06-04T23:17:25+02:00] INFO: Processing ruby_block[update-java-alternatives] action create (java::openjdk line 55)
[2013-06-04T23:17:25+02:00] INFO: ruby_block[update-java-alternatives] called
[2013-06-04T23:17:25+02:00] INFO: Processing package[sun-java6-jdk] action purge (java::default line 29)
[2013-06-04T23:17:25+02:00] INFO: Processing package[sun-java6-bin] action purge (java::default line 29)
[2013-06-04T23:17:25+02:00] INFO: Processing package[sun-java6-jre] action purge (java::default line 29)
[2013-06-04T23:17:25+02:00] INFO: Chef Run complete in 61.42747 seconds
[2013-06-04T23:17:25+02:00] INFO: Running report handlers
[2013-06-04T23:17:25+02:00] INFO: Report handlers complete
```