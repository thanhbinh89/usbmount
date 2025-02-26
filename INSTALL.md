# HOW TO USING THIS REPO
## Pull source
    git clone https://github.com/rbrito/usbmount.git
## Install dependencies
    sudo apt-get update && sudo apt-get install -y debhelper build-essential
## Build sources
    cd usbmount
    sudo dpkg-buildpackage -us -uc -b
  #### ** The ouput file at ../usbmount_0.0.24_all.deb **
## Install
    sudo dpkg -i ../usbmount_0.0.24_all.deb
  #### ** Run install dependencies and install again if see error **
    sudo apt-get install -f
## Config mountpoint to alway mount to /media/usb0
    sudo vi /etc/usbmount/usbmount.conf
#### Edit MOUNTPOINTS to: 
    MOUNTPOINTS="/media/usb0"
## Create scripts to restart docker services after mount successfully
    sudo vi /etc/usbmount/mount.d/01_restart_service
#### Add this line to file then close:
    sudo docker restart media upload
#### Change permission to excute
    sudo chmod +x /etc/usbmount/mount.d/01_restart_service
