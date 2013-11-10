# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.network :private_network, ip: "10.10.10.10"
  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.synced_folder "app", "/home/vagrant/app", :create => true, :nfs => true

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe "apt"
    chef.add_recipe "build-essential"
    chef.add_recipe "git"
    chef.add_recipe "nodejs"
    chef.add_recipe "mongodb::10gen_repo"
    chef.add_recipe "mongodb::default"

    chef.json.merge!({
      :nodejs => {
        :version => "0.10.21"
      }
    })
  end

end
