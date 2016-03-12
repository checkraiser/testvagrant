# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "bento/ubuntu-14.04"

  config.vm.network "forwarded_port", guest: 3100, host: 3100

  config.vm.provider "vmware_fusion" do |vf|
    vf.vmx["memsize"] = "1024"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {ansible_ssh_user: "vagrant"}
    ansible.sudo = true
  end

end