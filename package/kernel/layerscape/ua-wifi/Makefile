#
# Copyright 2017 NXP
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ua-wifi
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/fslwifi.git
PKG_SOURCE_VERSION:=0428548eab85a6e62726a10d6a2339c891162818
PKG_LICENSE:=GPL-2.0

include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

define KernelPackage/ua-wifi
  SUBMENU:=Wireless Drivers
  TITLE:=LA1575A IEEE 802.11 Wireless Interface Driver
  URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/fslwifi.git
  DEPENDS:=+kmod-mac80211
  FILES:=$(PKG_BUILD_DIR)/src/fslwifi.ko
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/src \
		KDIR="$(LINUX_DIR)" \
		ARCH="$(LINUX_KARCH)" \
		CROSS_COMPILE="$(TARGET_CROSS)"
endef

$(eval $(call KernelPackage,ua-wifi))
