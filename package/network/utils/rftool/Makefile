#
# Copyright 2017 NXP
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rftool
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/ua-rf-util.git
PKG_SOURCE_VERSION:=82d22c8ef06a110cbcf6a405b6847b1dcfb06bfb

include $(INCLUDE_DIR)/package.mk

define Package/rftool
  SECTION:=net
  CATEGORY:=Network
  TITLE:=rf tool
  URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/ua-rf-util.git
endef

MAKE_FLAGS += \
	KERNEL_DIR="$(LINUX_DIR)" \
	PWD="$(PKG_BUILD_DIR)" \
	-Wno-error=format-security

define Package/rftool/install
	mkdir -p $(1)/usr/bin $(1)/usr/lib $(1)/etc/config/catena_scripts
	$(CP) $(PKG_BUILD_DIR)/rftool/rftool $(1)/usr/bin/rftool
	$(CP) $(PKG_BUILD_DIR)/rflib/rflib.a $(1)/usr/lib/rflib.a
	$(CP) $(PKG_BUILD_DIR)/config/CATENA/* $(1)/etc/config/catena_scripts
endef

$(eval $(call BuildPackage,rftool))
