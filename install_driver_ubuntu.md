
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


# install CUDA 8.0
go to the link here and choose the right version cuda

http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html


download the *.run file and then follow the command:

or run


```
wget https://developer.nvidia.com/compute/cuda/8.0/Prod2/local_installers/cuda_8.0.61_375.26_linux-run
```
to get the cuda 8.0 for the ubuntu 14.04



