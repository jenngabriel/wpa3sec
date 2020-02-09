include $(TOPDIR)/rules.mk

PKG_NAME:=ath_masker
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vanhoefm/ath_masker
PKG_SOURCE_VERSION:=ebba51090061ab17065526ad7d9d7d6c1256b1ed
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.xz
PKG_MIRROR_HASH:=395dcae508a5ec88aa06143799d47418ab7f5f171011f2fa63e49d3d225d7e46

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/kernel.mk

define KernelPackage/ath_masker
  SUBMENU:=Other modules
  TITLE:=Kernel module to help spoof multiple MAC addresses
  FILES:=$(PKG_BUILD_DIR)/ath_masker.ko
endef

include $(INCLUDE_DIR)/kernel-defaults.mk

define Build/Compile
	$(MAKE) $(KERNEL_MAKEOPTS) SUBDIRS="$(PKG_BUILD_DIR)" modules
endef

$(eval $(call KernelPackage,ath_masker))
