# CAEAppCenter
Linux App to manage CAE applications distribution (using containers such as Singularity/Apptainer)

## pre-requisites
- gambas3, wget, singularity (or apptainer as "singularity" alias) 

## build
- open caeappcenter in Gambas3 v3.19+
- run / edit / build from there

## usage 
CAEAppCenter working principle is to allow the user to select CAE apps and download them from caelinux.com repository.

The apps will be installed in user's home directory at ~/cae/apps

Each app is stored in a sub folder, in the form of a Singularity / Apptainer container image (.sif)
## 
CAEAppCenter is also used to run the app either in GUI or in Shell mode

- run caeappcenter 
- see text area at the bottom to read messages : 
if all goes well, CAEAppCenter will download repository.xml file from https://caelinux.com/repo/  
- in the list view above, you should see the list of available / installed CAE apps: right click on one app to show its "context menu"
- in the context menu: you can choose either
  - Install : to download the app to ~/cae/apps
  - Remove : to delete the app from your computer (remove the subdir in ~/cae/apps)
  - Run : Run in "Main mode", usually in a GUI
  - Run SHell : Run a Shell (terminal) in the container image, to run commands interactivelly
  
## Disclaimer
Please note that this application is currently in its first beta stage (functionnal, but without much "safe guards"), use it at you own risks

## List of applications (current state 16.8.2025), see https://www.caelinux.com/repo/ for full list
- Salome-Meca 2024 / Code-Aster 17.4 MPI (Singularity container): CAD system / Pre-Post processor and advanced non-linear thermo mechanics FE solver
- FreeCAD v1.0.2 (official AppImage) : versatile 3D CAD & CAE platform
- ElmerFEM CSC (8.2025) (Singularity constainer): multi-physics FEM solver & GUI
- PrePoMax v2.3.0 & Calculix (Wine / autoinstaller): non-linear thermo-mechanics solver (Calculix) with efficient GUI (PrePoMax)
- HelyxOS & OpenFOAM v7 (Singularity container): OpenFOAM v7 CFD/multiphysics solver with HELYXOS v2.4 GUI (old but still functionnal)
- OpenRadioss (Singularity container, dev in progress) : Advanced non-linear explicit FE solver (can use INP files from PrePoMax as input)

## TODO lsit:
- add "post install" script in repository.xml and app => DONE, instead we use a custom launcher.sh script that runs the first time
- build packages for different distros, try portable appimage? or flatpak? => DONE
- add automated install of singularity or apptainer  => DONE : integrated relocatable apptainer install in the .AppImage
- add instructions to install singularity & other pre-requisites 
- add settings window to change defaults (like app path, terminal, etc..)
- correctly update text area (scroll to end...)
- show app specific Icon
- add longer description in repository.xml and  print it when selecting app in list
- add versionning system to apps (need to reformat repository.xml and dir structure...)
- check file integrity with checksum
- add support for external URLs for file download...
- add support for other type of "runtimes" like ...


