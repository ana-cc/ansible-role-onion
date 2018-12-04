# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

ENV['ANSIBLE_ROLES_PATH'] = "#{File.dirname(__FILE__)}/../"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # VirtualBox.
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.cpus = 1
  end

  # Ubuntu Precise (12.04 LTS)
  config.vm.define "precise" do |precise|
    precise.vm.hostname = "precise"
    precise.vm.box = "ubuntu/precise64"

    # Ansible.
    precise.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.become = true
    end
  end

  # Ubuntu Trusty (14.04 LTS)
  config.vm.define "trusty" do |trusty|
    trusty.vm.hostname = "trusty"
    trusty.vm.box = "ubuntu/trusty64"

    # Ansible.
    trusty.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.become = true
    end
  end

  # Debian Wheezy
  config.vm.define "wheezy" do |wheezy|
    wheezy.vm.hostname = "wheezy"
    wheezy.vm.box = "debian/wheezy64"

    # Ansible.
    wheezy.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.become = true
    end
  end

  # Debian stretch
  config.vm.define "stretch", primary: true do |stretch|
    stretch.vm.hostname = "stretch"
    stretch.vm.box = "debian/stretch64"

    # Ansible.
    stretch.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.become = true
    end
  end
end
