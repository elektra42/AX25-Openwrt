#
# Copyright (C) 2007-2021 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

# Name, version and release number
# The name and version of your package are used to define the variable to point to the build directory of your package:
#$(PKG_BUILD_DIR)
PKG_NAME:=ax25-tools
PKG_VERSION:=0.0.10-rc5
PKG_RELEASE:=1

PKG_MAINTAINER:=Elektra Wagenrad onelektra@gmx.net


# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
PKG_SOURCE:=ax25-tools-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.linux-ax25.org/pub/ax25-tools
PKG_MD5SUM:=b8cf1495820c445013c3776babcd057d

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

# Package definition; instructs on how and where our package will appear in the overall configuration menu ('make menuconfig')
define Package/ax25-tools
	SECTION:=Utils
	CATEGORY:=Amateur-Radio
	TITLE:=ax25 tools for hamradio applications
	URL:=http://www.linux-ax25.org/
	MAINTAINER:=Elektra Wagenrad onelektra@gmx.net
	DEPENDS:=+kmod-ax25 +libax25 +zlib
endef

# Package description; a more verbose description on what our package does
define Package/ax25-tools/description
	This library is for ham radio applications that use the ax25
	protocol.  Included are routines to do ax25 address parsing, common
	ax25 application config file parsing, etc.
endef

PKG_BUILD_DEPENDS:=libax25

define Package/ax25-tools/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/kissattach $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/kissnetd $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/kissparms $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/mkiss $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/net2kiss $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/ax25d $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/axparms $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/axctl $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/axspawn $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/axwrapper $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/beacon $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/bpqparms $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/mheard $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/mheardd $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rxecho $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/axgetput $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rsdwnlnk $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rsattach $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rsmemsiz $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rsuplnk $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/ax25_call $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/netrom_call $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/rose_call $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/tcp_call $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/m6pack $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/netromd $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/nodesave $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/nrattach $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/nrparms $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/nrsdrv $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/bget $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/bput $(1)/usr/bin/
endef

$(eval $(call BuildPackage,ax25-tools))
