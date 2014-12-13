# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "zauberpony/wheezy"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder "src/", "/var/www", owner: "www-data", group: "www-data"

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "aux/site.yml"
  end

  if Vagrant.has_plugin?("vagrant-cachier")
      config.cache.scope = :box
  end
end
