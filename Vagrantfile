# Vagrant for dev VM for esp-open-sdk mainly
#
# Kriek Jooste/kokeycode@speakopen.org
#

Vagrant.configure(2) do |config|
  config.vm.box = "ARTACK/debian-jessie"

  config.vm.provision "shell", inline: <<-SHELL
  	sudo apt-get update
  	sudo apt-get install -y make autoconf automake libtool gcc g++ gperf flex bison texinfo gawk ncurses-dev libexpat-dev python python-serial sed git
	sudo apt-get install -y libtool-bin unrar-free unzip vim picocom
	echo syntax on >> /etc/vim/vimrc
	su - vagrant -c 'git clone https://github.com/pfalcon/esp-open-sdk.git'
	su - vagrant -c 'cd esp-open-sdk && make'
	ln -s /home/vagrant/esp-open-sdk /opt/
	cd /opt
	su - vagrant -c 'git clone https://github.com/esp8266/source-code-examples.git'
	echo export PATH=/opt/esp-open-sdk/xtensa-lx106-elf/bin:\$PATH >> /home/vagrant/.bashrc
	echo export PATH=/opt/esp-open-sdk/xtensa-lx106-elf/bin:\$PATH >> /root/.bashrc
	ln -s /opt/esp-open-sdk/xtensa-lx106-elf/bin/esptool.py /usr/local/bin
	# todo: add USB serial filter
  SHELL
end
