# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "base"
  config.vm.box = "chef/centos-6.5"

  config.vm.define "vagrant-networking" do |node|
      node.vm.network "private_network", ip: "192.168.24.45"
      node.vm.hostname = "vagrant-networking"
  end

# This should already be in the box.
$script = <<SCRIPT
if [ ! -f /tmp/vagrant-base-packages-installed ]; then
  yum makecache && \
  yum install -y libselinux-python python python-pycurl && \
  touch /tmp/vagrant-base-packages-installed
fi
SCRIPT

  config.vm.provision "shell", inline: $script

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "networking.yml"
    ansible.verbose = "vvvv"
    ansible.host_key_checking = false
  end



end
