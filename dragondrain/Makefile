include $(TOPDIR)/rules.mk

PKG_NAME:=dragondrain
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vanhoefm/dragondrain-and-time
PKG_SOURCE_VERSION:=82616a731032b0abca69acebfeda4574960bd5f4
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.xz
PKG_MIRROR_HASH:=7727eba1efe98aeeb955712ab5b1e2c480d964ffc5f6a7437914f6d8d74acb05

PKG_FIXUP:=autoreconf
PKG_INSTALL=1

include $(INCLUDE_DIR)/package.mk

define Package/dragondrain
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Tools for the Dragondrain attack
  URL:=https://github.com/vanhoefm/dragondrain-and-time
  DEPENDS:=+libopenssl +zlib +libnl-tiny +libstdcpp
endef

define Package/dragondrain/description
	The Dragondrain tool forges Commit messages to cause a high CPU usage
	on the target. This can for example be used to drain the battery of a
	device, or more generally to drain and exhaust resources.
endef

TARGET_CPPFLAGS := \
	-D_GNU_SOURCE \
	-I$(STAGING_DIR)/usr/include/libnl-tiny \
	-I$(PKG_BUILD_DIR) \
	$(TARGET_CPPFLAGS) \
	-I$(LINUX_DIR)/user_headers/include

define Package/dragondrain/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/sbin $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,dragondrain))
