# espdevbox

This is a Vagrant development environment for the esp8266.

It consists of:
* a Debian Jessie Vagrant box
* The esp-open-sdk from https://github.com/pfalcon/esp-open-sdk

It would normally have access to the host system's USB port, which allows the burning of newly
compiled firmware over the USB UART to the esp8266 module.

To use this:
* install vagrant and the virtualisation environment you want to use with it (usually Virtualbox)
* go to the directory the Vagrantfile from this project is in
* do `vagrant up`

This will download the Debian vagrantbox, which could take a while.  It will also clone the 
esp-open-sdk and download its dependencies and build it, which can easily take at least half
and hour depending on the speed of your system

Once done, you can `vagrant ssh` to get to a shell on the box and clone git from git, or
start a new project.  esptool.py is also in the path to burn firmware to the esp8266 module.

The esp-open-sdk will be in /opt and the compiler in the path.
