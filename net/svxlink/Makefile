#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=svxlink
PKG_VERSION:=19.09.1
PKG_RELEASE:=1

PKG_SOURCE:=svxlink-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sm0svx/svxlink/archive/$(PKG_VERSION).tar.gz?
PKG_HASH:=5e5cbc3501fa6c6ec68334f8217ef93f5dc879d4d0e41e6f71378fd67d69f6a2

PKG_INSTALL:=1 
PKG_BUILD_PARALLEL:=1

PKG_MAINTAINER:=Najdanovic Ivan <najdanovicivan@gmail.com>
PKG_LICENSE:=GPL

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
CMAKE_SOURCE_SUBDIR:=src
CMAKE_BINARY_SUBDIR:=src
CMAKE_OPTIONS:=-DUSE_QT=No

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/svxlink/Default
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Instant Messaging
  TITLE:=SvxLink
  DEPENDS:=+libsigcxx +libgsm +libpopt +libgcrypt +libspeex +libopus +alsa-lib +tcl +librtlsdr +libcurl
  URL:=https://www.svxlink.org/
endef

define Package/svxlink
$(call Package/svxlink/Default)
endef

define Package/svxlink/description
  SvxLink server daemon.
endef

define Package/svxlink/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/devcal $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/remotetrx $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/siglevdetcal $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/svxlink $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/svxreflector $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/svxlink_gpio_down $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/svxlink_gpio_up $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/etc/svxlink
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/.procmailrc $(1)/etc/svxlink/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/TclVoiceMail.conf $(1)/etc/svxlink/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/gpio.conf $(1)/etc/svxlink/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/remotetrx.conf $(1)/etc/svxlink/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.conf $(1)/etc/svxlink/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxreflector.conf $(1)/etc/svxlink/
	$(INSTALL_DIR) $(1)/etc/svxlink/svxlink.d
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleDtmfRepeater.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleEchoLink.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleFrn.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleHelp.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleMetarInfo.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleParrot.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModulePropagationMonitor.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleSelCallEnc.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleTclVoiceMail.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_CONF) $(PKG_INSTALL_DIR)/etc/svxlink/svxlink.d/ModuleTrx.conf $(1)/etc/svxlink/svxlink.d/
	$(INSTALL_DIR) $(1)/usr/share/svxlink
	$(CP) $(PKG_INSTALL_DIR)/usr/share/svxlink/* $(1)/usr/share/svxlink/
	$(INSTALL_DIR) $(1)/var/spool/svxlink
	$(CP) $(PKG_INSTALL_DIR)/var/spool/svxlink/* $(1)/var/spool/svxlink/
endef

$(eval $(call BuildPackage,svxlink))

