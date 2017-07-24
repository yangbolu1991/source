#
# Copyright 2017 NXP
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=ua-avi
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/ua-avi.git
PKG_SOURCE_VERSION:=0068e5c544337caf0f5c93838d56285a2bf97e08

include $(INCLUDE_DIR)/package.mk

define Package/ua-avi
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=ua-avi
  URL:=http://B47093@sw-stash.freescale.net/scm/dnnpi/ua-avi.git
  DEPENDS:=+lua
endef

MAKE_FLAGS += \
	KERNEL_DIR="$(LINUX_DIR)" \
	PWD="$(PKG_BUILD_DIR)"

define Package/ua-avi/install
	$(MAKE) -C $(PKG_BUILD_DIR) \
		PWD="$(PKG_BUILD_DIR)" \
		install
	mkdir -p $(1)/etc/config/config_lua_scripts/ \
		$(1)/usr/bin \
		$(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/install/etc/config/config_lua_scripts/* \
		$(1)/etc/config/config_lua_scripts
	$(CP) $(PKG_BUILD_DIR)/install/usr/bin/* $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/install/usr/lib/* $(1)/usr/lib
endef

$(eval $(call BuildPackage,ua-avi))
