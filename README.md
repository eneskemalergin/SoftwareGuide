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
  - ```sudo apt update && sudo apt upgrade -y```
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
- **Remove snap package manager** It has couple of problems with the themes and icons as well as the updates. 
  - ```snap list``` - gets packages installed
  - ```sudo snap remove <name-of-the-package>``` - remove the packages installed
  - ```sudo apt purge snapd```
  - ```sudo rm -rf ~/snap /snap /var/snap /var/lib/snapd```
  
## Core Software

- **Install general use software and libraries:**
  - ```sudo apt install gdebi-core```
  - ```sudo apt install vim git htop```
  - ```sudo apt install openjdk-11-jdk build-essential libcurl4```
  - ```sudo apt install software-properties-common apt-transport-https wget```
  - ```sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev```
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
  - ```wget -q https://packagecloud.io/AtomEditor/atom/gpgkey -O- | sudo apt-key add -```
  - ```sudo add-apt-repository "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main"```
- **Install LaTex and related tools to use it:**
  - ```sudo apt install texlive-latex-extra```
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
  - ```sudo apt install gimp```
  - ```sudo apt install inkscape```
- **Configure Git:** Store the credentials and never ask them after initial username and password.
  - ```git config --global credential.helper store```
- **Install Anaconda for Python and R Ecosystem:**
  - Refer to this markdown explaining my use of anaconda - [Setup for Python and R](https://github.com/eneskemalergin/SoftwareGuide/blob/master/python_and_r_setup.md)

## Misc Software

- **Install VLC**
  - ```sudo apt install vlc```
- **Install Slack**
  - Download slack from [the link](https://slack.com/downloads/linux)
  - ```cd ~/Downloads/```
  - ```sudo apt install ./slack-desktop-4.11.3-amd64.deb```
- **Install LibreOffice**
  - ```sudo apt install libreoffice-gnome libreoffice```
- **Install BleachBit**
  - ```sudo apt install bleachbit```
- **Install PIA**
  - Download the linux installer from [the link](https://www.privateinternetaccess.com/installer/x/download_installer_linux)
  - ```cd ~/Downloads/```
  - ```bash pia-linux-2.5.1-05676.run```
  - Enter system memory for root/sudo
  - Login with credentials in the GUI
- **Install Calibre Ebook Server**
  - ```sudo apt install libfontconfig libgl1-mesa-glx```
  - ```sudo -v && wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sudo sh /dev/stdin```  
- **Install GlobalProtect**
  - Get the linux installer given by IT
  - Extract the file
  - ```sudo deb -i sudo dpkg -i GlobalProtect_deb-4.1.0.0-91.deb```
- **Configure Groupdrive Access through GlobalProtect**
  - Add GlobalProtect connect and disconnect in the bashrc
  - Connect Global Protect then enter the group drive server address
  - Add the server to the bookmark
  
## Beautifying Ubuntu for more Personality

- **Gnome Tweak Tool:** offering more control over the system especially on visual aspects.
  - ```sudo apt install gnome-tweaks```
- **Gnome Shell Extensions:** best tool to extend the customization of the system.
  - ```sudo apt install gnome-shell-extensions```
  - First activate the the extensions on Gnome Tweak tool tab called Extensions
  - ```sudo apt-get install chrome-gnome-shell```
    - OpenWeather
- **New Theme for System**:
  - Flat-Remix:
    - ```sudo add-apt-repository ppa:daniruiz/flat-remix```
    - ```sudo apt update```
    - ```sudo apt install flat-remix-gnome flat-remix-gtk flat-remix```
  - Numix:
    - ```sudo apt install numix-gtk-theme```
    - ```sudo add-apt-repository ppa:numix/ppa```
    - ```sudo apt install numix-icon-theme numix-icon-theme-circle numix-icon-theme-square```
