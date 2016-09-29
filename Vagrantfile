# -*- mode: ruby -*-
# vi: set ft=ruby :

unless Vagrant.has_plugin?("vagrant-docker-compose")
  system("vagrant plugin install vagrant-docker-compose")
  puts "Dependencies installed, please try the command again."
  exit
end

unless Vagrant.has_plugin?("vagrant-vbguest")
  system("vagrant plugin install vagrant-vbguest")
  puts "Dependencies installed, please try the command again."
  exit
end

Vagrant.configure(2) do |config|
  config.vm.box = "bento/ubuntu-14.04"
  config.vm.network "private_network", ip: "192.168.56.103"

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.provision :shell, inline: "apt-get update"

  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/docker-compose.yml", run: "always"

  config.vm.provision :shell, path: "./bootstrap.sh"

end
