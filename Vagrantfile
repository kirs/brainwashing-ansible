# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  "vagrant0" => "192.168.33.10"
}

Vagrant.configure("2") do |config|
  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "precise32"
      machine.vm.box_url = "http://files.vagrantup.com/precise32.box"
      machine.vm.hostname = "%s.example.org" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
        v.name = name
        v.customize ["modifyvm", :id, "--memory", 200]
      end
    end
  end
end
