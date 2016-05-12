# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network :forwarded_port, guest:80, host:3000

  config.vm.provider :virtualbox do |vb|
    vb.memory = '2048'
    vb.cpus = 2
  end

  config.ssh.insert_key = false

  config.vm.provision :shell, :inline => <<__END
    set -eu
    wget -qO- https://get.docker.com/ | sh
    mkdir -p /var/discourse
    git clone https://github.com/discourse/discourse_docker.git /var/discourse
__END

end
