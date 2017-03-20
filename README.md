## My Software Guide for Research Computer

### Specs of my computer

__Operating System and System type / version:__ Ubuntu 16.04.2 LTS

__Processor type and speed:__ Intel i5 6600K, 3.5 GHz

__RAM amount:__ 64GB

__GPU:__ Nvidia 1070 gtx, 8GB

__Hard drive size:__ 1 TB SSD, 3TB SATA


### Steps to Software Installation/Configuration
- Install Nvidia drivers
  > We will install the latest Nvidia drivers because apt-get will give us old versions, [Nvidia Download Website](http://www.nvidia.fr/Download/index.aspx)

  - ```sudo service lightdm stop```
  - ```ctrl+alt+f2```
  - ```sudo init 3```
  - ```sudo sh NVIDIA-Linux-x86_64-375.39.run```
  - ```sudo reboot```

- Install some required packages:

  - ```sudo apt-get install openjdk-8-jdk git build-essential libcurl3-dev```
  - ```sudo apt-get install software-properties-common```

- Installing CUDA
  > We will first install the toolkit Go to [Nvidia CUDA Website](https://developer.nvidia.com/cuda-release-candidate-download). Choose **Linux > x86_64 > Ubuntu > 16.04 > runfile (local)**

  > Say no when asked if you want to install the driver because we installed the latest version already.

  - ```sudo sh cuda_8.0.61_375.26_linux.run```

  - Install cuDNN
    > Go to [Nvidia cuDNN website](https://developer.nvidia.com/cudnn) download the latest for CUDA 8.0 and linux (cuDNN v5.1)

    ```BASH
    $ sudo tar -xzvf cudnn-8.0-linux-x64-v5.1.tgz
    $ sudo cp cuda/include/cudnn.h /usr/local/cuda/include
    $ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
    $ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
    ```


  > Now we have to update the paths in .bashrc

  ```BASH
  nano ~/.bashrc
  ```

  Add following to the bottom of the file and save.

  ```BASH
  export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64"
  export CUDA_HOME=/usr/local/cuda
  ```

  Now we need to reload the .bashrc and we will check if the paths are properly modified.

  ```BASH
  source ~/.bashrc
  echo $CUDA_HOME
  echo $PATH
  echo $LD_LIBRARY_PATH
  ```

- Install Bazel

  > You can find instructions from [Bazel](http://www.bazel.io/docs/install.html) Website too.

  ```BASH
  $ echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list
  $ curl https://storage.googleapis.com/bazel-apt/doc/apt-key.pub.gpg | sudo apt-key add -
  $ sudo apt-get update
  $ sudo apt-get install bazel
  $ sudo apt-get upgrade bazel
  ```

- Install Anaconda Python Distribution
  > Anaconda distribution is really easy Python distributor that I can manage my libraries.

  - Download Anaconda Python 3.6 from [here](https://www.continuum.io/downloads)
  - ```bash Downloads/Anaconda3-4.3.1-Linux-x86_64.sh```

- Install Tensorflow

  > To prepare TensorFlow installation and running, we need to create a conda environment, say, called ```tensorflow```

  - ```conda create -n tensorflow```
  - ```source activate tensorflow```
  - ```pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.0.1-cp36-cp36m-linux_x86_64.whl```

  > Check if the installation is working:

  - ```python```
  - ```import tensorflow```

  > You should see something like this:

  ```BASH
  I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcublas.so locally
  I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcudnn.so locally
  I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcufft.so locally
  I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcuda.so.1 locally
  I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcurand.so locally
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

- Installing R Kernels for Jupyter
  > RStudio is an amazing environment, but I am really used to using Jupyter Notebooks for notes and tutorials. I will be installing R Essentials bundle with 80 popular libraries to install R Kernel.

  - ```conda install -c r r-essentials```
