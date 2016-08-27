======================
=Setup=
======================
*Raspberry pi (rpi)*

Without monitor
=====================
So we want to setup a raspberry but don't have an monitor and the cable or don't want to
use it, then here are what need to prepare:


* prepare ethernet cable
* SD card with raspbian 
* a linux computer (virtual box is ok [#]_)
* rpi
* wifi Adapter (rpi2 only) and wifi 


1. 將 SD 卡接上電腦打開 terminal 輸入 ``lsblk`` 會列出電腦上現在有的設備
   ::
      NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
      sda      8:0    0    64G  0 disk
      ├─sda1   8:1    0    63G  0 part /
      ├─sda2   8:2    0     1K  0 part
      └─sda5   8:5    0  1022M  0 part [SWAP]
      sdb      8:16   1   7.5G  0 disk
      ├─sdb1   8:17   1    60M  0 part
      └─sdb2   8:18   1   7.4G  0 part /media/petercheng/23c4ddbc-85fa-4cea-b96b-edae
      sr0     11:0    1  1024M  0 rom
      sr1     11:1    1  1024M  0 rom

      
   ``sda`` 是自己電腦上硬碟， we can see that sda1 is mount at ``/``. If you computer detect the SD card, there will
   be a disk beside your old disk, here is ``sdb``, we can see that ``sdb`` has two partition, ``sdb1`` and ``sdb2``. ``sdb1`` is
   the boot directory and it's unmounting now, you can mount it manually via ``mount -t [fs type] dev dir``.
   ``sdb2`` is the root directory of raspbian, it is automatically mounted at ``/media/petercheng/.....``. Inside it,
   there is a directory ``etc/``. And it is where we are going to change the setting. 

2. ``cd`` into ``etc/network`` and edit the ``interfaces``. We are going to manually give your raspberry a private ip.
   Add following to the file:
   ::
      auto eth0  #ethernet 0 
      allow-hotplug eth0
      iface eth0 inet static   
        #you can change it to the ip you want
        address 2.2.2.2  #It is an abnormal ip address I know, you can find a common-used private ip if it doesn't work 
	netmask 255.255.255.0
	gateway 2.2.2.1

      #below is for wifi
      auto wlan0  #wireless LAN
      allow-hotplug wlan0
      iface wlan inet dhcp
      #using the dhcp, you can also set the static ip for it if you want


3. ``cd`` into ``etc/wpa_supplicant/`` and edit the ``wpa_supplicant.conf``. Here is where it save the WIFI configuration.
   Add following to the file::
      network={
        #there are more things that you can set, go search by yourslef
        ssid="<name of your wifi>"
	psk ="<password of wifi>"
      }


4. Back to your own computer, change the ethernet setting. set the ip under the same subnet.
   for example::
     address = 2.2.2.3       #this can't be the same of your raspberry
     netmask =255.255.255.0  #but is same here
     

5. 到這邊設定就完成了，接下來就接上網路線透過 SSH 連進去就可以啦

   open the terminal and enter ``ssh pi@2.2.2.2`` and password is ``raspberry``

   
Reference
====================
.. [#] `virtualbox 設定教學`_
.. _virtualbox 設定教學: https://docs.google.com/document/d/1yHEs6f24kBEpDVxC2qtJtUBQl8mDpx5aCM5umrBoYxg/edit
