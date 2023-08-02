#
# Copyright (C) 2006-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libsigc++
PKG_VERSION:=2.12.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNOME/libsigc++/2.12
PKG_HASH:=1c466d2e64b34f9b118976eb21b138c37ed124d0f61497df2a90ce6c3d9fa3b5

PKG_MAINTAINER:=Najdanovic Ivan <najdanovicivan@gmail.com>
PKG_LICENSE:=LGPL-3.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=meson/host

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

MESON_ARGS += \
        -Dbuild-examples=false

define Package/libsigcxx
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=typesafe callback system for standard C++
  URL:=https://libsigcplusplus.github.io/libsigcplusplus/
  DEPENDS:=+libstdcpp
endef

define Package/libsigcxx/description
 It allows you to define signals and to connect those signals to any
 callback function, either global or a member function, regardless of
 whether it is static or virtual.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
		$(1)/usr/lib/pkgconfig/

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libsigc-2.0.so* \
		$(1)/usr/lib/

	$(INSTALL_DIR) $(1)/usr/lib/sigc++-2.0/include
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/sigc++-2.0/include/*.h \
		$(1)/usr/lib/sigc++-2.0/include

	$(INSTALL_DIR) $(1)/usr/include/sigc++-2.0/sigc++
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/sigc++-2.0/sigc++/*.h \
		$(1)/usr/include/sigc++-2.0/sigc++

	$(INSTALL_DIR) $(1)/usr/include/sigc++-2.0/sigc++/adaptors
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/sigc++-2.0/sigc++/adaptors/*.h \
		$(1)/usr/include/sigc++-2.0/sigc++/adaptors

	$(INSTALL_DIR) $(1)/usr/include/sigc++-2.0/sigc++/adaptors/lambda
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/sigc++-2.0/sigc++/adaptors/lambda/*.h \
		$(1)/usr/include/sigc++-2.0/sigc++/adaptors/lambda

	$(INSTALL_DIR) $(1)/usr/include/sigc++-2.0/sigc++/functors
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/sigc++-2.0/sigc++/functors/*.h \
		$(1)/usr/include/sigc++-2.0/sigc++/functors

endef

define Package/libsigcxx/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libsigc-2.0.so* \
		$(1)/usr/lib/
endef

$(eval $(call BuildPackage,libsigcxx))
