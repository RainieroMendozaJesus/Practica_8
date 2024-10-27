Vagrant.configure("2") do |config|
    # Configura la box de Vagrant
    config.vm.box = "ubuntu/bionic64" # Puedes elegir otra box si lo prefieres
  
    # Asigna recursos a la máquina virtual
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512" # Asignar 512 MB de RAM
      vb.cpus = 1       # Asignar 1 CPU
    end
  
    # Configura el directorio compartido
    config.vm.synced_folder "./paginas_web", "/var/www/html"
  
    # Provisionamiento para instalar Apache
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
      sudo systemctl start apache2
      echo "<h1>Hola Mundo</h1>" | sudo tee /var/www/html/index.html
    SHELL
  end

  Vagrant.configure("2") do |config|
    config.vm.box = "nombre_de_tu_caja"
  
    # Reenvío de puertos: desde el puerto 8080 del anfitrión al puerto 80 de la VM
    config.vm.network "forwarded_port", guest: 80, host: 8080
  end
  
  