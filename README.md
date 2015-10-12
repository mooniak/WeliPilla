# WeliPilla
Welipilla is a [hindkit](https://github.com/itfoundry/hindkit) based build system for font compiling and interpolation. [Vagrant](https://www.vagrantup.com/) is used to remove platform dependancies and WeliPilla can be used on any major Operating system.  
**This repository is just a boilerplate to show where things go. To get a clear idea of this build system please refer our working font projects such as [this](https://github.com/mooniak/stick-no-bills-font).**
##Dependancies
* [Vagrant](https://www.vagrantup.com/)
* [Virtual Box](https://www.virtualbox.org/)  

##Folder Structure
Some of the folders, which should be present on a actual font project is not visible here due to gitignore. Following folders are essential for the build process.
|--masters  
|--build  
|--sources  
|--instances  
|--scripts  

* masters: Where master ```ufo``` files reside
* build: Compiled ```.otf``` goes here
* sources: Source ```ufo``` files resides here.(Since we use FontForge at Mooniak we use sub folder named ```sfd``` to put our working files and using the build script we convert them to ```ufo```at build)
* instances: Interpolated font instances will go here
* scripts: Contains all the build scripts

##Building WeliPilla based project
* Install above two dependencies  
* Go to cloned project using terminal and run ```$vagrant up```. This will spawn a Ubuntu 12 virtual machine and provision it with all the dependencies for hindkit, hindkit and fontforge. At first time this will take about 10-20 minutes depending on your Internet connection.  

**On Unix based systems**  
* After above command run ```$vagrant ssh``` and it will open a ssh connection to newly spawned VM.  

**On Windows based systems**  
* Download SSH tool like [putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
* Enter the IP and the port of VM. This will be shown when Vagrant machine is starting up.(Normally IP is ```127.0.0.1``` or ```localhost```.If you dont have any other VMs running, most proberbly the port will be 2222).
* Use ```vagrant``` as username and password when prompted. (You can use private key authentication if you want). It will open a ssh connection to newly spawned VM. 
  
  
* After connecting to VM run```$cd /vagrant/scripts``` This will take you into the scripts folder of font project.
* Run ```./builder.sh```. It will build your font and put ```otf``` files in build directory.

##Who does what..
There few scripts serving the build process.
* /Vagrantfile: Contains details on which Vagrant box to use, which is the provisioning script and etc.
* /buil.py: hindkit config file for the font. **Welipilla uses ITF, hindkit as build tool.** Refer [hindkit](https://github.com/itfoundry/hindkit) for more details on this file.
* /scripts/bootstrap.sh: This is the provisioning script for Vagrant VM.
* /scripts/merger.py: This Python script is used to combine two or more ```ufo``` objects in to one.
* /scripts/fontconvert: This script is used to convert ```sfd``` files to ```ufo``` object using FontForge Python interface.
* /scripts/builder.sh: This shell script contains shell commands to run above scripts with necessary arguments.
