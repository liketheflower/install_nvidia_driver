# install_nvidia_driver


Hit Ctrl+Alt+F1 and login using your credentials.      

First of all I suggest removing all nvidia drivers.   

```sh 
sudo apt-get purge nvidia*  
```

kill your current X server session by typing ```sh sudo service lightdm stop ``` or ```sh sudo lightdm stop```          
Enter runlevel 3 by typing sudo init 3            
Install your *.run file.       
you change to the directory where you have downloaded the file by typing for instance cd Downloads. If it is in another directory, go there. Check if you see the file when you type ls NVIDIA*           
Make the file executable with chmod +x ./your-nvidia-file.run       
Execute the file with sudo ./your-nvidia-file.run        
You might be required to reboot when the installation finishes. If not, run sudo service lightdm start or sudo start lightdm to start your X server again.        




# reference 1

https://askubuntu.com/questions/636620/cannot-install-nvidia-driver-for-ubuntu-14-04    

First of all I suggest removing all nvidia drivers.

sudo apt-get purge nvidia*
For Ubuntu 14.04 the default and preferred driver is nvidia-331.

It can be installed by

 sudo apt-get install nvidia-331
As an option you can upgrade kernel and install newer drivers.

Upgrade kernel to 3.19

sudo apt-get install linux-generic-lts-vivid
reboot

Then install nvidia-346 from xorg-edgers

sudo add-apt-repository ppa:xorg-edgers/ppa
sudo apt-get update
sudo apt-get install nvidia-346 nvidia-prime nvidia-settings
sudo add-apt-repository -r ppa:xorg-edgers/ppa
Look for errors when install. In most cases the driver works well, but it depends on graphical stack version installed, your integrated adapter model, etc.

If the driver does not work and graphics does not start, press Ctrl+Alt+F1, login to console and run

sudo apt-get purge nvidia*







#  reference 2

https://askubuntu.com/questions/149206/how-to-install-nvidia-run   


Hit Ctrl+Alt+F1 and login using your credentials.  
kill your current X server session by typing sudo service lightdm stop or sudo lightdm stop  
Enter runlevel 3 by typing sudo init 3  
Install your *.run file.  
you change to the directory where you have downloaded the file by typing for instance cd Downloads. If it is in another directory, go there. Check if you see the file when you type ls NVIDIA*  
Make the file executable with chmod +x ./your-nvidia-file.run  
Execute the file with sudo ./your-nvidia-file.run  
You might be required to reboot when the installation finishes. If not, run sudo service lightdm start or sudo start lightdm to start your X server again.  
