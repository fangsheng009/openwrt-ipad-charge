# 
# Copyright (C) 2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ipad-charge
PKG_VERSION:=2013-02-17
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/mkorenkov/ipad_charge.git
PKG_SOURCE_VERSION:=953f1e7a7078333d79c9c56a3d480fe5152698e2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=

include $(INCLUDE_DIR)/package.mk

define Package/ipad-charge
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libusb-1.0
  TITLE:=Apple charger utility
endef

define Package/ipad-charge/description
Enables USB charging for Apple devices, e.g. iPad.
endef

define Package/ipad-charge/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/usb $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ipad_charge $(1)/usr/sbin/ipad_charge
	$(INSTALL_DATA) ./files/ipad-charge.hotplug $(1)/etc/hotplug.d/usb/40-ipad-charge
endef

$(eval $(call BuildPackage,ipad-charge))
