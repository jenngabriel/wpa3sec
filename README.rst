==============================
 OpenWRT Feed for Dragondrain
==============================

Usage
=====

* Download openwrt, e.g.::

   git clone https://github.com/openwrt/openwrt

* Setup the feed

  Your OpenWRT directory should contain a ``feeds.conf``. Add the following line::

   src-git wpa3sec https://github.com/foo/myfeed

* Install the feed::

   ./scripts/feeds update myfeed
   ./scripts/feeds install -a -p myfeed

* Configure the packages::

   make menuconfig


