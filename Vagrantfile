Vagrant.configure("2") do |config|
    config.vm.box = "generic/arch"
    config.vm.synced_folder ".", "/home/vagrant/dev"
    config.vm.provision "shell", reboot: true, inline: <<-SHELL
        sudo pacman -Syu --noconfirm docker docker-compose 
        sudo usermod -aG docker vagrant
        sudo systemctl enable docker.service
    SHELL
end
