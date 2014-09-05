VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "berendt/devstack-ubuntu-14.04-amd64"

  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 6080, host: 8081, host_ip: "127.0.0.1"

  config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1384"]
  end

  config.vm.provision "shell", privileged: false, inline: "/home/vagrant/devstack/stack.sh"

end
