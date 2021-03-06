# vagrant-testservers
Quickly deploy a few Centos Testservers with Vagrant, very handy for testing stuff or practicing with RHEL7.
## Prerequisites
Install VirtualBox
Install Vagrant
Install Vargant plugin vagrant-hostmanager
## Howto
Clone this repo and run Vagrant:
```sh
git clone https://github.com/scorputty/vagrant-testservers.git
cd vagrant-testservers
vagrant up
```
This will install two testserver nodes, testserver1 and testserver2. You can login to them with:
```sh
vagrant ssh testserverX
```
or use regular ssh to login
```
ssh vagrant@testserverX (pass = vagrant)
```
If you want more or less nodes to play with you need to edit this field in the Vagrantfile:
```ruby
TESTSERVER = 2
```
## Note
Your sudo pass might be asked to enable the hostmanager plugin to update your hosts file.
## Note 2
The password is always "vagrant" for both the vagrant user as for the root account!
## Note 3
This has only been tested on Mac OSX, but it should work on any Vagrant capable system.
## Note 4
Adjust the network range in the Vagrantfile to suit your specific needs.
```ruby
node.vm.network :private_network, ip: "192.168.0.%d" % (10 + i )
```
