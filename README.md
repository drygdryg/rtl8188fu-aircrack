For Kernel 4.15.x ~ 5.7.x (Linux Mint, Ubuntu or Debian Derivatives)

------------------

## How to install (for arm devices)

`sudo apt-get install build-essential git dkms linux-headers-$(uname -r)`

`git clone git clone -b arm https://github.com/kelebek333/rtl8188fu rtl8188fu-arm`

`sudo dkms add ./rtl8188fu-arm`

`sudo dkms build rtl8188fu/1.0`

`sudo dkms install rtl8188fu/1.0`

`sudo cp ./rtl8188fu/firmware/rtl8188fufw.bin /lib/firmware/rtlwifi/`

------------------

Run following commands for disable power management and plugging/replugging issues.

`sudo mkdir -p /etc/modprobe.d/`

`sudo touch /etc/modprobe.d/rtl8188fu.conf`

`echo "options rtl8188fu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/rtl8188fu.conf`

------------------

## How to uninstall

`sudo dkms remove rtl8188fu/1.0 --all`

`sudo rm -f /lib/firmware/rtlwifi/rtl8188fufw.bin`

`sudo rm -f /etc/modprobe.d/rtl8188fu.conf`


