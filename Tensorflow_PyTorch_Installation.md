# Configuration Guide to Install PyTorch and Tensorflow v2 with GPU on 18.04

Content is taken mostly with some changes from [mc.ai blogpost](https://mc.ai/the-ultimate-ubuntu-deep-learning-installation-guide-cuda-tensorflow-keras-opencv-pytorch/).


## Content
1. [Installing Ubuntu Packages](#installing_ubuntu_packages)
2. [GPU Related Installation](#gpu_related_installation)


## Installing Ubuntu Packages

- ```sudo apt-get update```
- ```sudo apt-get install libjpeg-dev libpng-dev libtiff-dev```
- ```sudo apt-get install build-essential cmake unzip pkg-config```
- ```sudo apt-get install libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev```
- ```sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev```
- ```sudo apt-get install libgtk-3-dev```
- ```sudo apt-get install libhdf5-serial-dev```
- ```sudo apt-get install libxvidcore-dev libx264-dev```
- ```sudo apt-get install libopenblas-dev libatlas-base-dev liblapack-dev gfortran```


## GPU Related Installation

It’s better to install CUDA before the display driver; otherwise, CUDA installation error might occur. We’ll not be using CUDA 10.1 because of its incompatibility with some deep learning packages.

To get the NVIDIA Graphic Drivers in UBUNTU:
- ```sudo add-apt-repository ppa:graphics-drivers/ppa```
- ```sudo apt-get update```

### Installing CUDA Toolkit

- Download the linux/x86_64/Ubuntu/18.04/runfile(local) in [CUDA 10.0 install link](https://developer.nvidia.com/cuda-10.0-download-archive)
- ```chmod +x cuda_10.0.130_410.48_linux.run```
- ```sudo ./cuda_10.0.130_410.48_linux.run --override```
- Following installer:
  - Say n to installing **Install NVIDIA Accelerated Graphics Driver** & **X config**
  - Say y for others

Adding CUDA to Environment Path:

```shell
# NVIDIA CUDA Toolkit
export PATH=/usr/local/cuda-10.0/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64
```
- Then source the bashrc to apply the changes.
- Check if CUDA is installed properly: ```nvcc -V```

### Installing Nvidia Driver

Before finishing this step, your computer display should not be able to have HD resolution. If you do, that’s because your Ubuntu automatically installed the Nouveu driver for you (Not a good thing)

> Nvidia drivers change in Ubuntu quite a lot needs to be updated for handling multiple deep learning libraries.

- [The fix](https://linuxconfig.org/how-to-disable-nouveau-nvidia-driver-on-ubuntu-18-04-bionic-beaver-linux)
- [Nvidia driver download](https://www.nvidia.com/Download/Find.aspx)
- I recommend version 430.4 because I haven’t ran into any compatibility issues with it so far.
- ```chmod +x NVIDIA-Linux-x86_64–430.40.run```
- ```sudo ./ NVIDIA-Linux-x86_64–430.40.run```
- Then Reboot the computer: ```reboot```

### Installing cuDNN
This is the NVIDIA CUDA® Deep Neural Network library. It will be used for installing the gpu-accelerated libraries (eg. opencv)

- [Signup & download cuDNN](https://developer.nvidia.com/cudnn)
- ```tar -zxf file_name```
- ```cd cuda```
- ```sudo cp -P lib64/* /usr/local/cuda/lib64/```
- ```sudo cp -P include/* /usr/local/cuda/include/```


### Installing Tensorflow and PyTorch
- ``` conda install tensorflow-gpu```
- ``` conda install pytorch-gpu```


