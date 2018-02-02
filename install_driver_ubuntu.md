
# how to install GPU driver for Titan Xp based on ubuntu 14.04
```
sudo apt-get purge nvidia*
sudo add-apt-repository ppa:graphics-drivers
sudo apt-get update
sudo apt-get install nvidia-390
sudo reboot
```
it worked very well.
reference

http://www.linuxandubuntu.com/home/how-to-install-latest-nvidia-drivers-in-linux


# install CUDA 8.0(incomplete)
go to the link here and choose the right version cuda

http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html


download the *.run file and then follow the command:

or run


```
wget https://developer.nvidia.com/compute/cuda/8.0/Prod2/local_installers/cuda_8.0.61_375.26_linux-run
```
to get the cuda 8.0 for the ubuntu 14.04



# install cuda8.0(workable for the lab)
Install CUDA for Ubuntu

There is an Linux installation guide. 
  http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#axzz4jHO99tiV

Download NVIDIA CUDA Toolkit: "runfile (local)". That is 1.1 GB.
  https://developer.nvidia.com/cuda-downloads

Check the md5 sum. Only continue if it is correct.
```
  md5sum cuda_7.5.18_linux.run
```
Remove any other installation.
```
  sudo apt-get purge nvidia-cuda*
  ```
if you want to install the drivers
```
  sudo apt-get purge nvidia-*
  ```

Logout from your account 
  On the login screen, go to a terminal session:
    ctrl+alt+F2
  Stop lightdm:
  ```
    sudo service lightdm stop
    ```
  Create a file at /etc/modprobe.d/blacklist-nouveau.conf with the following contents:
  ```
    blacklist nouveau 
    options nouveau modeset=0
    ```
  Then regenerate the kernel initramfs:
  ```
    sudo update-initramfs -u
    ```

Run cuda installer. Follow the command-line prompts
```
  sudo sh cuda_7.5.18_linux.run --override
  ```

Start lightdm again:
```
  sudo service lightdm start
  ```

Restart computer:
```
  sudo reboot
  ```

Post Installation:
  Add this path to the PATH variable:
  ```
    export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}
    ```
  Change the environment variables for 64-bit operating systems:
  ```
    export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64\
      ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
      ```
  Try running nvcc, if you get this output it works:
  ```
    nvcc -V
    ```
    nvcc: NVIDIA (R) Cuda compiler driver
    Copyright (c) 2005-2016 NVIDIA Corporation
    Built on Tue_Jan_10_13:22:03_CST_2017
    Cuda compilation tools, release 8.0, V8.0.61

2nd version:
export PATH=$PATH:/usr/local/cuda-8.0/bin
vi ~/.profile
paste export PATH=$PATH:/usr/local/cuda-8.0/bin at end of file
source ~/.profile


# good reference 

https://medium.com/@acrosson/installing-nvidia-cuda-cudnn-tensorflow-and-keras-69bbf33dce8a
