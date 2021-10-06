## File server
---

```bash
#install the required modules for the server
sudo apt-get install nfs-common nfs-server

#get the ip of the server
ifconfig

#make a directory to be shared
mkdir /home/pi/Documents/Shared
sudo chown -R 777 /home/pi/Documents/Shared

#edit the exports file
sudo nano /etc/exports
#/home/pi/Documents/Shared "*(rw,anonuid=1000,anongid=1000)"

#update from the exports file
sudo exportfs
```

```bash
#install client requirements
sudo apt-get install nfs-common

#create folder to be linked
mkdir /home/pi/Documents/Shared
sudo chown -R pi:pi /home/pi/Documents/Shared

#mount the remote drive at the created directory
sudo mount ip:/home/pi/Documents/Shared /home/pi/Documents/Shared
```