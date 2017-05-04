Vagrant.configure(2) do |config|
        config.vm.box = "ubuntu/xenial64"

        config.vm.network "public_network"
        #config.vm.network "forwarded_port", guest: 80, host: 80  #port forward for NAT

        config.vm.provision "shell", inline: <<-SHELL
                sudo apt-get update
                sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
                sudo apt-add-repository 'deb https://apt.dockerproject.org/repo ubuntu-xenial main'
                sudo apt-get update
                sudo apt-get install -y docker-engine
                sudo usermod -aG docker ubuntu
                sudo apt-get install -y python-pip
                sudo pip install docker-compose
        SHELL
end
