# Software Guide Ubuntu 18.04 Edition
---

## Specs of The Computer

__Operating System and System type / version:__ Ubuntu 18.04.02 LTS

__Processor type and speed:__ Ryzen 7 2700x, 16 Threat, 3.7 to 4.3 GHz

__RAM amount:__ 32GB

__GPU:__ Nvidia 1060 gtx, 6GB

__Hard drive size:__  1 TB SSD, 3TB SATA

## Configuring Options after default Installation:

- **Enable Additional Repositories:** expanding the amount of packages by allowing other main ubuntu repositories.
  - Search and Open -> Software & Update App
  - Go to other software tab -> enable Canonical Partners

- **Accessing Flatpack:** for getting system from Fedora. This will get Flatpack applications in Ubuntu Software Center.
  - ```sudo apt install flatpak```
  - ```sudo apt install gnome-software-plugin-flatpak```
  - ```flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo```

- **Update the System**: it's better to have the most updated packages and software
  - ```sudo apt update```
  - ```sudo apt upgrade```
  - ```sudo apt dist-upgrade```
  - *```ubuntu-support-status```* allows you to look at which packages are currently supported.


- **Install Media Codecs and Extras**
  - ```sudo apt install ubuntu-restricted-extras```
  - ```sudo apt install libavcodec-extra```
  - ```sudo apt install libdvd-pkg```

## Installing Core Software

- **Gdebi debian Installer:**
  - ```sudo apt install gdebi-core```

> In this section I will be putting,  graphics drives, gpu computation drives installation. However I didn't work on it when I write this so it will be for the next time.

- **Installing general Use software:**
  - ```sudo apt-get install openjdk-8-jdk build-essential libcurl3-dev```
  - ```sudo apt-get install vim git htop
  - ```sudo apt-get install software-properties-common```

- **Installing Anaconda Python Distribution for Python 3.6**:
  - Download the bash script from [the website](https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh)
  - ```bash Anaconda3-5.2.0-Linux-x86_64.sh```
  - ```rm Anaconda3-5.2.0-Linux-x86_64.sh```, after installed.

- **Installing Google Chrome:** the default browser to be used.
  ```BASH
  wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
  sudo gdebi google-chrome-stable_current_amd64.deb
  rm google-chrome-stable_current_amd64.deb
  ```

- **Installing git**
  - ```sudo apt-get install git```
  - ```git config --global user.name "name"```
  - ```git config --global user.email "email"```

- **Installing Atom Text Editor:**
  - Download atom debian file from [the website](https://atom.io/)
  - ```sudo gdebi atom-amd64.deb```

- **Installing Latex and Related Tools:**
  - ```sudo apt install texlive-latex-extra```
  - Atom editor could be used to create-compile-preview latex documents.
  - Install *latex* package in Atom installation tab
    - Enable *Build on Save*
    - *Enable SyncTeX*
    - *Enable DiCy*
  - Install *pdf-view* package
    - Enable *Auto reload on update*
  - Configure *spell-check* from atom installation tab
    - Add *text.tex.latex* to Grammer section
  - Install *language-latex* package

- **Installing R and RStudio:**
  - ```sudo apt update```
  - ```sudo apt install libxml2-dev libssl-dev libcurl4-openssl-dev libopenblas-dev r-base r-base-dev```
  - Download the Rstudio debian installer from [the website](https://www.rstudio.com/products/rstudio/download/#download)
  - ```sudo gdebi ~/Downloads/rstudio-xenial-1.1.456-amd64.deb```
  - ```rm ~/Downloads/rstudio-xenial-1.1.456-amd64.deb```
  - ```sudo apt install libnetcdf-dev libexpat1 libexpat1-dev libpoppler-cpp-dev default-jre default-jdk r-cran-rjava libfreetype6-dev libgtk2.0-dev libxt-dev libcairo2-dev```
  - Installing packages with a Script:
    - You need to update the list of package names in the repositiory called bioconductor/cran/github_packages.txt
    - Then run the script.


- **Installing and Configuring Thunderbird Email Client**
  - ```sudo apt install thunderbird```

- **Installing GIMP for image editing**:
  > This is a similar software like Photoshop for linux

  - ```sudo add-apt-repository ppa:otto-kesselgulasch/gimp-edge```
  - ```sudo apt update && sudo apt install gimp gimp-gmic```

- **Install Inkscape for Vector Design**:
  > This is a open source software that does similar job as Adobe Illustrator

  - ```sudo add-apt-repository ppa:inkscape.dev/stable```
  - ```sudo apt update && sudo apt install inkscape```

- **Installing VLC for Video**:
  - ```sudo apt install vlc```


### Third-Party Software

- Install GooglePlayMusic Desktop Player
  - [Link to Installer Website](https://www.googleplaymusicdesktopplayer.com)
  - Install it with Gdebi installer

- Install BleachBit
  > To keep things neat and clean
  - [Link to Installer](https://www.bleachbit.org/download/file/t?file=bleachbit_1.12_all_ubuntu1604.deb)
  - Install it with Gdebi installer

- Install PomoDoneApp
  > This is the time tracking app that I've integrated with Trello
  - [Link to Installer](https://app.pomodoneapp.com/installers/PomoDoneApp-1.5.1084.deb)
  - Install it with Gdebi installer

- Install Slack
  > Slack is a group messaging app.
  - [Link to Install Page](https://slack.com/downloads/linux)
  - Install it with Gdebi installer


## Beautifying Ubuntu for Personal Joy

- **Gnome Tweak Tool**: Offers more control over the system especially on visual aspects.
  - ```sudo apt install gnome-tweak-tool```

- **Gnome Shell Extensions**: best tool to extend the customization of the linux system.
  - First activate the the extensions on Gnome Tweak tool tab called *Extensions*
  - ```sudo apt-get install chrome-gnome-shell```
  - Then visiting and looking for extensions on [official extension page](https://extensions.gnome.org/)
  -
