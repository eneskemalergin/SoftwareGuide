## My Software Guide for Research Computer

### Specs of my computer

__Operating System and System type / version:__ Ubuntu 16.04.1

__Processor type and speed:__ Intel i5 6600K, 3.5 GHz

__RAM amount:__ 64GB

__GPU:__ Nvidia 1070 gtx, 8GB

__Hard drive size:__ 500GB SSD, 3TB SATA


### Steps to Software Installation/Configuration
- Install Nvidia drivers
  > We will install the latest Nvidia drivers because apt-get will give us old versions, [Nvidia Download Website](http://www.nvidia.fr/Download/index.aspx)

  - ```sudo service lightdm stop```
  - ```ctrl+alt+f2```
  - ```sudo init 3```
  - ```sudo sh NVIDIA-Linux-x86_64-375.30.run```
  - ```sudo reboot```

- Installing CUDA
  > We will first install the toolkit Go to [Nvidia CUDA Website](https://developer.nvidia.com/cuda-release-candidate-download). Choose **Linux > x86_64 > Ubuntu > 16.04 > runfile (local)**

  > Say no when asked if you want to install the driver because we installed the latest version already.

  - ```sudo sh cuda_8.0.61_375.26_linux.run --override```

  > Now we have to update the paths in .bashrc

  ```BASH
  cd
  gedit .bashrc
  ```

  Add following to the bottom of the file and save.

  ```BASH
  export CUDA_HOME=/usr/local/cuda-8.0
  export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}
  export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
  ```

  Now we need to reload the .bashrc and we will check if the paths are properly modified.

  ```BASH
  source ~/.bashrc
  echo $CUDA_HOME
  echo $PATH
  echo $LD_LIBRARY_PATH
  ```

- Install cuDNN
  > Go to [Nvidia cuDNN website](https://developer.nvidia.com/cudnn) download the latest for CUDA 8.0 and linux

  ```BASH
  tar xvzf cudnn-8.0-linux-x64-v5.1.tgz
  cd cuda
  sudo cp include/cudnn.h /usr/local/cuda-8.0/include/
  sudo cp lib64/* /usr/local/cuda-8.0/lib64/
  ```


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

  - ```mkdir ~/.icons```
  - ```sudo apt install unity-tweak-tool```
  - ```sudo add-apt-repository ppa:noobslab/icons2```
  - ```sudo apt-get update```
  - ```sudo apt-get install square-icons```
  - Open unity tweak tool
  - Appearance > Icons > select square-light or square-dark

- Install Anaconda Python Distribution
  > Anaconda distribution is really easy Python distributor that I can manage my libraries.

  - Download Anaconda Python 3.6 from [here](https://www.continuum.io/downloads)
  - ```bash Downloads/Anaconda3-6.1.1-Linux-x86_64.sh```

- Install tensorflow with GPU

  - Create virtual machine
  - ```conda create -n tf python=3.6```
  - ```source activate tf```
  - ```pip install --upgrade pip```
  - ```pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.10.0rc0-cp27-none-linux_x86_64.whl```


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

- Install Octave and Octave Kernel for Jupyter
  > I like to use octave for fast machine learning model prototyping. And of course I love to use octave in my best notebook. (for non-GUI octave use ```octave-cli``` command in terminal)

  > To install Octave I use PPA:

  - ``` sudo apt-add-repository ppa:octave/stable ```
  - ``` sudo apt-get update```
  - ``` sudo apt-get install octave```

  > Now let's install octave kernel for Jupyter from conda-forge:

  - ```conda install -c conda-forge octave_kernel=0.25.1```
