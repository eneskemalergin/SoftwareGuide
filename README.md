## My Software Guide for Research Computer

### Specs of my computer

__Operating System and System type / version:__ Ubuntu 20.04.1 LTS

__Processor type and speed:__ Ryzen 7 3950x, 32 Threat, 3.5 to 4.7 GHz

__RAM amount:__ 32GB

__GPU:__ Nvidia RTX 2080 Super, 8GB

__Hard drive size:__ 1 TB M.2 SSD, 2TB SATA


### Steps to Software Installation/Configuration
- Install Nvidia drivers
  > Ubuntu 20.04's additional drivers installs NVIDIA drivers. 

- Install some required packages:

  - ```sudo apt-get install openjdk-8-jdk git build-essential libcurl3-dev```
  - ```sudo apt-get install software-properties-common```

> *Deep Learning related packages installation is moved to its own file.*

- Install Anaconda Python Distribution
  > Anaconda distribution is really easy Python distributor that I can manage my libraries.

  - Download Anaconda Python 3.6 from [here](https://www.continuum.io/downloads)
  - ```bash Downloads/Anaconda3-4.3.1-Linux-x86_64.sh```

- Install Jupyter Themes 
  > Installing the most updated version of jupyterthemes
  - ```pip install --upgrade jupyterthemes```
  - ```jt -t solarizedl -T -N``` 
  

- Install Tensorflow

  - For dependencies: ```sudo apt-get install libcupti-dev```
  - Then we install Tensorflow with pip: ```pip install tensorflow-gpu```


- Install Chrome

  ```BASH
  wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
  sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
  sudo apt-get install -f
  rm google-chrome-stable_current_amd64.deb
  ```
  > <span style="color:red">If chrome lags when you highlight or something just go and unchecked Use 'Hardware acceleration if available' in advance settings of chrome settings</span>

- Configure workspaces in Ubuntu

  - system settings > Appearance > Behavior > Check 'Enable Workspaces'
  - If you want to configure new shortcuts:
    - System Settings > Keyboard > Shortcuts > Navigation > You can assign new shortcuts

- Install gdebi package manager
  > Gdebi is a better way to install deb files for me.
  - ```sudo apt-get install gdebi```

- Install vim
  - ```sudo apt-get install vim```

- Install git
  - ```sudo apt-get install git```
  - ```git config --global user.name "name"```
  - ```git config --global user.email "email"```

- Install htop
  > It is really nice command line tool to see and control system
  - ```sudo apt-get install htop```

- Install Atom text editor

  - ```sudo add-apt-repository ppa:webupd8team/atom```
  - ```sudo apt-get update```
  - ```sudo apt-get install atom```

- Install Restricted Extras for Ubuntu
  > package of several codecs that are not included by default in Ubuntu system, media codecs and Flash Support.
  - ```sudo apt-get install ubuntu-restricted-extras```

- Install a good Theme for Ubuntu
  > It is really nice to have a new look...

   - ```sudo apt install unity-tweak-tool```
   - ```sudo apt-add-repository ppa:numix/ppa```
   - ```sudo apt-get update```
   - ```sudo apt-get install numix-gtk-theme```
   - ```sudo apt-get install numix-icon-theme numix-folders```
   - ```sudo apt-get install numix-icon-theme-circle```
   - ```sudo apt-get install numix-icon-theme-square```
   - Open unity tweak tool
   - Select __Appearance > Theme and Icons__

- Install a Latex related tools 
  > When I create reports I create from Jupyter Notebook to PDF and Latex is the intermediary step of it.
  - ```sudo apt update && sudo apt install texlive-full```

- Install R and RStudio
  > I love R since it's amazing tool for statistics and learning mathematical background of most algorithms. Also Rstudio is really high quality interpreter for R.

  - ```sudo echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" | sudo tee -a /etc/apt/sources.list```
  - ```gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9```
  - ```gpg -a --export E084DAB9 | sudo apt-key add -```
  - ```sudo apt-get update```
  - ```sudo apt-get install r-base r-base-dev```
  - ```sudo apt-get install gdebi-core```
  - ```wget https://download1.rstudio.org/rstudio-xenial-1.1.383-amd64.deb```
  - ```sudo gdebi -n rstudio-xenial-1.1.383-amd64.deb```
  - ```rm rstudio-xenial-1.1.383-amd64.deb```

- Installing needed development packages for some of R libraries

  - ```sudo apt-get install libnetcdf-dev```
  - ```sudo apt install libcurl4-openssl-dev libssl-dev libxml2-dev```
  - ```sudo apt-get install libexpat1 libexpat1-dev```

- Install Mendeley Desktop 
  > Mendeley is a beautiful way to keep track of papers.
  
  - ```wget https://www.mendeley.com/repositories/ubuntu/stable/amd64/mendeleydesktop-latest```
  - ```sudo dpkg -i mendeleydesktop```
  - ```sudo apt-get update```
  - ```sudo rm mendeleydesktop```

- Install Redshift (Night Shift software)
  > Since I usually work at night and the light from the screen is too much, so I use redshift and configure it.
  
  - ```sudo apt-get install redshift gtk-redshift geoclue```
  - ```vim ~/.config/redshift.conf```
  - Copy and Paste the following in the vim:
  ```BASH
  ; Global settings for redshift
  [redshift]
  ; Set the day and night screen temperatures
  temp-day=4500
  temp-night=3500

  ; Enable/Disable a smooth transition between day and night
  ; 0 will cause a direct change from day to night screen temperature.
  ; 1 will gradually increase or decrease the screen temperature
  transition=1

  ; Set the screen brightness. Default is 1.0
  ;brightness=0.8
  ; It is also possible to use different settings for day and night since version
  ; 1.8.
  brightness-day=0.9
  brightness-night=0.7
  ; Set the screen gamma (for all colors, or each color channel individually)
  gamma=0.8
  ;gamma=0.8:0.7:0.8

  ; Set the location-provider. Type 'redshift -l list' to see possible values.
  ; The location provider settings are in a different section.
  location-provider=geoclue2

  ; Set the adjustment-method: 'randr', 'vidmode'
  ; type 'redshift -m list' to see all possible values
  ; 'randr' is the preferred method, 'vidmode' is an older API
  ; but works in some cases when 'randr' does not.
  ; The adjustment method settings are in a different section.
  adjustment-method=randr

  ; Configuration of the location-provider:
  ; type 'redshift -l PROVIDER:help' to see the settings
  ; ex: 'redshift -l manual:help'
  [manual]
  ; set these values if you've set the location-provider to manual instead of
  ; geoclue
  ;lat=51.522698
  ;lon=-0.085358

  ; Configuration of the adjustment-method
  ; type 'redshift -m METHOD:help' to see the settings
  ; ex: 'redshift -m randr:help'

  [randr]
  screen=0
  ```

- Install GIMP for image editing
  > This is a similar software like Photoshop for linux
  
  - ```sudo add-apt-repository ppa:otto-kesselgulasch/gimp-edge```
  - ```sudo apt update && sudo apt install gimp gimp-gmic```
  
- Install Inkscape for Vector Design
  > This is a open source software that does similar job as Adobe Illustrator 
  
  - ```sudo add-apt-repository ppa:inkscape.dev/stable```
  - ```sudo apt update```
  - ```sudo apt install inkscape```
  
- Install VLC for Video
  - ```sudo apt install vlc```

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
  
