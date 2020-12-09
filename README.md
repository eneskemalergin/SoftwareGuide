# My Software Guide for Research Computer

## Specs of my computer

- __Operating System and System type / version:__ Ubuntu 20.04.1 LTS

- __Processor type and speed:__ Ryzen 7 3950x, 32 Threat, 3.5 to 4.7 GHz

- __RAM amount:__ 32GB

- __GPU:__ Nvidia RTX 2080 Super, 8GB

- __Hard drive size:__ 1 TB M.2 SSD, 2TB SATA

## After Default Install Configuration

- **Enable Additional Repos:** to expand the amount of packages by allowing other main ubuntu repositories.
  - Search and Open -> Software and Update App
  - Go to other software tab -> enable Canonical Partners
- **Update the System:** to update the system to most updated version. 
  - ```sudo apt-get update && sudo apt-get upgrade -y```
- **Install missing drivers:** Some drivers are installed automatically but at the time of writing I needed to install some hardware specific drivers.
  - Enable Nvidia driver:
    - Search and Open -> Software and Update App
    - Select *Additional Drivers* tab -> enable *nvidia-driver-450*
  - Install Realtek Ethernet Driver for B550 motherboard:
    - **Solution needs to be clarified and tested more - There are still some stability issues.**
- **Automount storage drive:** non-boot drives require manual mounting, I want to set up a auto-mount so I don't have to mount it all the time.
  - Find the name of the mount using this: ```sudo fdisk -l```
  - Find the UUID of the mount: ```sudo blkid```
  - Create a mount point: ```sudo mkdir /data```
  - The automount entry -> Open the fstab file for edit: ```sudo nano /etc/fstab```
    - Add this to the end of the file: ```UUID=CHANGE_WITH_UUID /data    auto nosuid,nodev,nofail,x-gvfs-show 0 0```

## Core Software

- **Install general use software and libraries:**
  - ```sudo apt install gdebi-core```
  - ```sudo apt install vim git htop```
  - ```sudo apt install openjdk-11-jdk build-essential libcurl4```
- **Install media codecs and extras:**
  - ```sudo apt install ubuntu-restricted-extras```
  - ```sudo apt install libavcodec-extra```
  - ```sudo apt install libdvd-pkg```
  
## Development Software

- **Install Google Chrome:**
  - ```wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb```
  - ```sudo gdebi google-chrome-stable_current_amd64.deb```
  - ```rm google-chrome-stable_current_amd64.deb```
- **Install Atom Editor:**
  - ```sudo snap install atom --classic```
- **Install LaTex and related tools to use it:**
  - I use Atom.io to create-compile-preview latex documents.
  - Install latex package in Atom installation tab
    - Enable Build on Save
    - Enable SyncTeX
    - Enable DiCy
  - Install pdf-view package
    - Enable Auto reload on update
  - Configure spell-check from atom installation tab
    - Add *text.tex.latex* to Grammer section
  - Install language-latex package
- **Install GIMP and InkScape:**
  - ```sudo snap install gimp```
  - ```sudo snap install inkscape```
- **Install Anaconda for Python and R Ecosystem:**
  - Refer to this markdown explaining my use of anaconda - [Setup for Python and R](https://github.com/eneskemalergin/SoftwareGuide/blob/master/python_and_r_setup.md)
- **Configure Git:** Store the credentials and never ask them after initial username and password.
  - ```git config --global credential.helper store```

## Misc Software

- **Install VLC**
  - ```sudo snap install vlc```
- **Install Slack**
  - ```sudo snap install slack --classic```
- **Install LibreOffice**
  - ```sudo snap install libreoffice```
- **Install BleachBit**
  - ```sudo apt install bleachbit```

## Beautifying Ubuntu for more Personality

- **Gnome Tweak Tool:** offering more control over the system especially on visual aspects.
  - ```sudo apt install gnome-tweaks```
- **Gnome Shell Extensions:** best tool to extend the customization of the system.
  - ```sudo apt install gnome-shell-extensions```
  - First activate the the extensions on Gnome Tweak tool tab called Extensions
  - ```sudo apt-get install chrome-gnome-shell```
    - OpenWeather
