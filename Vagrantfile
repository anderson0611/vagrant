Vagrant.configure("2") do |config|
  
    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/bionic64"
      web1.vm.hostname = "web1"
      web1.vm.network "private_network", ip: "dhcp"
      web1.vm.synced_folder "./html/web1", "/var/www/html"
  
      web1.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
        systemctl start apache2
      SHELL
    end
  
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
        web1.vm.box = "ubuntu/bionic64"
        web1.vm.hostname = "web1"
        web1.vm.network "private_network", ip: "dhcp"
        web1.vm.synced_folder "./html/web2", "/var/www/html"
    
        web1.vm.provision "shell", inline: <<-SHELL
          apt-get update
          apt-get install -y apache2
          systemctl enable apache2
          systemctl start apache2
        SHELL
      end