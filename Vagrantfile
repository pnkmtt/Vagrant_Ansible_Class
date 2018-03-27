#
# Single box with VirtualBox provider.
#
# NOTE: Make sure you have the precise32 base box installed...
# vagrant box add precise32 http://files.vagrantup.com/precise32.box
#
# VirtualBox modifyvm docs: http://www.virtualbox.org/manual/h08.html#vboxmanage-modifyvm

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial32"
  config.vm.hostname = "myxenial32.box"
  config.vm.network :private_network, ip: "192.168.0.42"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--cpuexecutioncap", "50",
      "--memory", "256",
    ]
  end
end