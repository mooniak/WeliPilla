# WeliPilla
Welipilla is a [hindkit](https://github.com/itfoundry/hindkit) based build system for font compiling and interpolation. [Vagrant](https://www.vagrantup.com/) is used to remove platform dependancies and WeliPilla can be used on any major Operating system.
##Dependancies
* [Vagrant](https://www.vagrantup.com/)
* [Virtual Box](https://www.virtualbox.org/)  

##Folder Stucture
Some of the folders, which should be present on a actual font project is not visible here due to gitignore. Following folders are essential for the build process.
|--masters  
|--build  
|--sources  
|--instances
|--scripts  

* masters: Where master ```ufo``` files reside
* build: Compiled ```.otf``` goes here
* sources: Source ```ufo``` files resides here
* instances: Interpolated font instances will go here
* scripts: Contains all the build scripts
