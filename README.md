## My Software Guide for Research Computer

### Specs of my computer

<Add Specs>


### Steps to Software Installation/Configuration
- Install Nvidia drivers
  >  

  - ```sudo add-apt-repository ppa:graphics-drivers/ppa```
  - ```sudo apt-get update```
  - ```sudo apt-get install nvidia-367```

- Install Chrome
  >

  - ```wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb```
  - ```sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb```
  - ```sudo apt-get install -f```
  - ```rm google-chrome-stable_current_amd64.deb```

  > <span style="color:red">If chrome lags when you highlight or something just go and unchecked Use 'Hardware acceleration if available' in advance settings of chrome settings</span>

- Configure workspaces in Ubuntu
  >

  - system settings > Appearance > Behavior > Check 'Enable Workspaces'
  - If you want to configure new shortcuts:
    - System Settings > Keyboard > Shortcuts > Navigation > You can assign new shortcuts

- Install vim
  >

  - ```sudo apt-get install vim```
- Install Atom text editor
  >

  - ```sudo add-apt-repository ppa:webupd8team/atom```
  - ```sudo apt-get update```
  - ```sudo apt-get install atom```

- Install a good Theme for Ubuntu
  > It is really nice to have a new look...

  - ```mkdir ~/.icons```
  - ```sudo apt install unity-tweak-tool```
  - ```sudo add-apt-repository ppa:noobslab/icons2```
  - ```sudo apt-get update```
  - ```sudo apt-get install square-icons```
  - Open unity tweak tool
  - Appearance > Icons > select square-light or square-dark

- Install Anaconda Python Distribution
  > Anaconda distribution is really easy Python distributor that I can manage my libraries.

  - Download Anaconda Python 2.7 from [here](https://www.continuum.io/downloads)
  - ```bash Downloads/Anaconda2-4.1.1-Linux-x86_64.sh```

- Install CUDA 8.0
  - You need to be a member of developer [link](https://developer.nvidia.com/cuda-release-candidate-download)
  - Download the .run file
  - ```sudo sh ./Downloads/cuda_8.0.27_linux.run```
  -


- Install tensorflow with GPU

- Install R and RStudio
  > I love R since it's amazing tool for statistics and learning mathematical background of most algorithms. Also Rstudio is really high quality interpreter for R.

  - ```sudo echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" | sudo tee -a /etc/apt/sources.list```
  - ```gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9```
  - ```gpg -a --export E084DAB9 | sudo apt-key add -```
  - ```sudo apt-get update```
  - ```sudo apt-get install r-base r-base-dev```
  - ```sudo apt-get install gdebi-core```
  - ```wget https://download1.rstudio.org/rstudio-0.99.896-amd64.deb```
  - ```sudo gdebi -n rstudio-0.99.896-amd64.deb```
  - ```rm rstudio-0.99.896-amd64.deb```
