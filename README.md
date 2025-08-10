# CAEAppCenter
Linux App to manage CAE applications distribution (using containers such as Singularity/Apptainer)

## pre-requisites
- gambas3, wget, singularity (or apptainer as "singularity" alias) 

## build
- open caeappcenter in Gambas3 v3.19+
- run / edit / build from there

## usage 
CAEAppCenter working principle is to allow the user to select CAE apps and download them from caeliux.com repository.

The apps will be installed in user's home directory at ~/cae/apps

Each app is stored in a sub folder, in the form of a Singularity / Apptainer container image (.sif)

CAEAppCenter is also used to run the app either in GUI or in Shell mode

- run caeappcenter 
- see text area at the bottom to read messages : 
if all goes well, CAEAppCenter will download repository.xml file from https://caeilinux.com/repo/  
- in the list view above, you should see the list of available / installed CAE apps: right click on one app to show its "context menu"
- in the context menu: you can choose either
  - Install : to download the app to ~/cae/apps
  - Remove : to delete the app from your computer (remove the subdir in ~/cae/apps)
  - Run : Run in "Main mode", usually in a GUI
  - Run SHell : Run a Shell (terminal) in the container image, to run commands interactivelly
  
## Disclaimer
Please note that this application is currently in its first alpha stage (functionnal, but without much "safe guards"), use it at you own risks

## TODO:
- add "post install" script in repository.xml and app => for example to run SalomeMeca "run --app install" the first time
- build binary package
- build packages for different distros, try portable appimage? or flatpak?
- add instructions to install singularity & other pre-requisites 
- add settings window to change defaults (like app path, terminal, etc..)
- correctly update text area (scroll to end...)
- show app specific Icon
- add longer description in repository.xml and  print it when selecting app in list
- add versionning system to apps (need to reformat repository.xml and dir structure...)
- check file integrity with checksum
- add support for external URLs for file download...
- add support for other type of "runtimes" like ...
- add automated install of singularity or apptainer ? 

