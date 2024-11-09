Vagrant.configure("2") do |config|
    # Caja base de Ubuntu
    config.vm.box = "ubuntu/bionic64"
  
    # Configuración de recursos
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    # Instalación de Apache en la VM
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
    SHELL
  
    # Configuración de carpeta compartida
    config.vm.synced_folder "./www", "/var/www/html"
  end