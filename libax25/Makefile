#
# Copyright (C) 2007-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

# Name, version and release number
# The name and version of your package are used to define the variable to point to the build directory of your package:
#$(PKG_BUILD_DIR)
PKG_NAME:=libax25
PKG_VERSION:=0.0.12-rc5
PKG_RELEASE:=1

PKG_MAINTAINER:=Elektra Wagenrad onelektra@gmx.net
PKG_LICENSE:=LGPL-2.1-only
PKG_LICENSE_FILES:=COPYING

#PKG_BUILD_DIR:=/home/elektra/SRC/clean_openwrt/elektrapackages/build/libax25-0.0.12-rc4

# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
PKG_SOURCE:=libax25-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.linux-ax25.org/pub/libax25
PKG_MD5SUM:=21e64a76d41f3129acc7b540730e2f4d

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

# Package definition; instructs on how and where our package will appear in the overall configuration menu ('make menuconfig')
define Package/libax25
	SECTION:=Libs
	CATEGORY:=Amateur-Radio
	TITLE:=ax25 library for hamradio applications
	URL:=http://www.linux-ax25.org/
	MAINTAINER:=Elektra Wagenrad
	DEPENDS:=+kmod-ax25
endef

# Package description; a more verbose description on what our package does
define Package/libax25/description
	This library is for ham radio applications that use the ax25
	protocol.  Included are routines to do ax25 address parsing, common
	ax25 application config file parsing, etc.
endef


define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/include/netax25
	$(INSTALL_DIR) $(1)/usr/include/netrose
	$(INSTALL_DIR) $(1)/usr/include/netrom
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/ipkg-install/usr/include/netax25/* $(1)/usr/include/netax25
	$(CP) $(PKG_BUILD_DIR)/ipkg-install/usr/include/netrose/* $(1)/usr/include/netrose
	$(CP) $(PKG_BUILD_DIR)/ipkg-install/usr/include/netrom/* $(1)/usr/include/netrom
	$(CP) $(PKG_BUILD_DIR)/ipkg-install/usr/lib/* $(1)/usr/lib
endef

define Package/libax25/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/$(PKG_NAME).so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libax25))
