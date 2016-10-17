# Microdia Chipset Driver for Ubuntu

Check if your Keyboard USB use Miccrodia chipset

~~~shell
lsusb
~~~

Installation

~~~shell
sudo apt-get install mercurial build-essential linux-headers-generic dkms
git clone https://github.com/dannyec/microdia.git
cd microdia
sudo ./install.sh dkms

vi /etc/modprobe.d/usbhid.conf
#Add:
options usbhid quirks=0x0c45:0x7603:0x0007

vi /etc/default/grub
#Add:
GRUB_CMDLINE_LINUX_DEFAULT='usbhid.quirks=0x0c45:0x7603:0x7'
~~~
