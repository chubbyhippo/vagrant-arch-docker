Vagrant.configure("2") do |config|
    config.vm.box = "generic/arch"
    config.vm.synced_folder ".", "/home/vagrant/dev"
    config.vm.provision "shell", inline: <<-SHELL
        sudo pacman -Syu --noconfirm docker docker-compose      
        sudo groupadd docker
        sudo usermod -aG docker vagrant
        sudo systemctl enable docker.service
        sudo reboot
    SHELL
end
