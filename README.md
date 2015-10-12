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
* ```$cd /vagrant/scripts``` This will take you into the scripts folder of font project.
* Run ```./builder.sh```. It will build your font and put ```otf``` files in build directory.
