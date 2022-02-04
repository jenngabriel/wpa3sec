==============================
 OpenWRT Feed for Dragondrain
==============================

Usage
=====

* Download openwrt, e.g.::

   git clone https://github.com/openwrt/openwrt

* Setup the feed

  Your OpenWRT directory should contain a ``feeds.conf``. Add the following line::

   src-git wpa3sec https://github.com/jenngabriel/wpa3sec

* Install the feed::

   ./scripts/feeds update wpa3sec
   ./scripts/feeds install -a -p wpa3sec

* Configure the packages::

   make menuconfig


