#
# Copyright (C) 2018 adron@yapic.net
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mtpoe-ctrl
PKG_SOURCE_VERSION:=b25f7f77dd2829341beb040acc06204e988d93d8
PKG_MIRROR_HASH:=27ea06ee8bf091011bfd36391747e8eedaea5e525da885c08757506456ae9774
PKG_VERSION:=1.15
PKG_RELEASE:=18

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/prudy/mtpoe_ctrl.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Sergey Sergeev <adron@yapic.net>
PKG_LICENSE:=GPL-2.0

include $(INCLUDE_DIR)/package.mk

define Package/mtpoe-ctrl
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libuci +kmod-spi-dev
  TITLE:=Management utility for Mikrotiks PoE V2/V3/V4
  URL:=$(PKG_SOURCE_URL)
endef

define Package/mtpoe-ctrl/description
	Management utility for Mikrotiks PoE V2/V3/V4
endef

define Package/mtpoe-ctrl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bins/mtpoe_ctrl $(1)/usr/bin/mtpoe-ctrl
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/openwrt/files/99_mtpoe-ctrl $(1)/etc/init.d/
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/openwrt/files/99_mtpoe-ctrl.defaults $(1)/etc/uci-defaults/
endef

$(eval $(call BuildPackage,mtpoe-ctrl))
