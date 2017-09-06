## My Software Guide for Research Computer

### Specs of my computer

__Operating System and System type / version:__ Ubuntu 16.04.2 LTS

__Processor type and speed:__ Ryzen 7 1700x, 16 Threat, 3.4 to 3.8 GHz

__RAM amount:__ 32GB

__GPU:__ Nvidia 1080 gtx, 8GB

__Hard drive size:__ 256 GB M.2 SSD, 1 TB SSD, 2TB SATA


### Steps to Software Installation/Configuration
- Install Nvidia drivers
  > ~~We will install the latest Nvidia drivers because apt-get will give us old versions, [Nvidia Download Website](http://www.nvidia.fr/Download/index.aspx)~~
  > Ubuntu 16.04 Nvidia ppa now has 375 and it seems stable so we will go with that now.

  - ```sudo add-apt-repository ppa:graphics-drivers/ppa```
  - ```sudo apt update```
  - ```sudo apt-get install nvidia-375```
  - ```sudo reboot``` # Restarts your system

- Install some required packages:

  - ```sudo apt-get install openjdk-8-jdk git build-essential libcurl3-dev```
  - ```sudo apt-get install software-properties-common```

- Installing CUDA
  > We will first install the toolkit Go to [Nvidia CUDA Website](https://developer.nvidia.com/cuda-release-candidate-download). Choose **Linux > x86_64 > Ubuntu > 16.04 > deb(local)**

  - ```sudo dpkg -i cuda-repo-ubuntu1604-8-0-local-ga2_8.0.61-1_amd64.deb```
  - ```sudo apt-get update```
  - ```sudo apt-get install cuda```

  > Then we add the path updates to the .bashrc with the following oneliners.

  - ```export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}```
  - ```export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}```

  > To test the CUDA if it's working:

  - ```cd /usr/local/cuda-8.0/samples/5_Simulations/nbody```
  - ```sudo make```
  - ```./nbody```


- Install cuDNN
    > Go to [Nvidia cuDNN website](https://developer.nvidia.com/cudnn) download the latest for CUDA 8.0 and linux  Carefull because we will be using cuDNN v5.1 for our setup.

    ```BASH
    $ sudo tar -xzvf cudnn-8.0-linux-x64-v5.1.tgz
    $ sudo cp cuda/include/cudnn.h /usr/local/cuda/include
    $ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
    $ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
    ```

- Install Anaconda Python Distribution
  > Anaconda distribution is really easy Python distributor that I can manage my libraries.

  - Download Anaconda Python 3.6 from [here](https://www.continuum.io/downloads)
  - ```bash Downloads/Anaconda3-4.3.1-Linux-x86_64.sh```

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

- Install R and RStudio
  > I love R since it's amazing tool for statistics and learning mathematical background of most algorithms. Also Rstudio is really high quality interpreter for R.

  - ```sudo echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" | sudo tee -a /etc/apt/sources.list```
  - ```gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9```
  - ```gpg -a --export E084DAB9 | sudo apt-key add -```
  - ```sudo apt-get update```
  - ```sudo apt-get install r-base r-base-dev```
  - ```sudo apt-get install gdebi-core```
  - ```wget https://download1.rstudio.org/rstudio-xenial-1.0.153-amd64.deb```
  - ```sudo gdebi -n rstudio-xenial-1.0.153-amd64.deb```
  - ```rm rstudio-xenial-1.0.153-amd64.deb```

- Install Mendeley Desktop 
  > Mendeley is a beautiful way to keep track of papers.
  
  - ```wget https://www.mendeley.com/repositories/ubuntu/stable/amd64/mendeleydesktop-latest```
  - ```sudo dpkg -i mendeleydesktop```
  - ```sudo apt-get update```
  - ```sudo rm mendeleydesktop```
