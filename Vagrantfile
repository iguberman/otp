# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # https://docs.vagrantup.com

  # boxes at https://atlas.hashicorp.com/search
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", ip: "192.168.33.10"


  config.vm.synced_folder "otp", "/otp"

  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end


  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
 
   sudo apt-get install docker -y > /dev/null 
# for erlang
   sudo apt-get install make -y > /dev/null
   sudo apt-get install git -y > /dev/null 
   sudo apt-get install autoconf  -y > /dev/null
   sudo apt-get install fop  -y > /dev/null
   sudo apt-get install libncurses5-dev  -y > /dev/null
   sudo apt-get install openjdk-6-jdk -y > /dev/null
   sudo apt-get install unixodbc-dev -y > /dev/null
   sudo apt-get install g++ -y > /dev/null
   sudo apt-get install libssl-dev -y > /dev/null
  
   # for wxwidgets used in erlang
   sudo apt-get install libwxbase2.8 -y > /dev/null
   sudo apt-get install libwxgtk2.8-dev -y > /dev/null
   sudo apt-get install libqt4-opengl-dev -y > /dev/null
   sudo apt-get install libgtk2.0-dev -y > /dev/null

   cd /otp
   ./autoconf
   ./otp_build autoconf
   ./configure
   #make
  SHELL


 

end
