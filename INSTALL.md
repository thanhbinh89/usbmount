# Install dependencies
    sudo apt-get update && sudo apt-get install -y debhelper build-essential

# Build sources
    cd usbmount && sudo dpkg-buildpackage -us -uc -b
  #### ** The ouput file at ../usbmount_0.0.24_all.deb **

# Install
    sudo dpkg -i ../usbmount_0.0.24_all.deb
  #### ** Run install dependencies and install again if error **
    sudo apt-get install -f

# Config mountpoint
    sudo vi /etc/usbmount/usbmount.conf
  #### ** if fix mountpoint alway is /mnt/usb, edit line 12 **
    MOUNTPOINTS="/mnt/usb"
