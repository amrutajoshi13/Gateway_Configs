#
# Copyright (C) 2008-2015 The LuCI Team <luci@lists.subsignal.org>
#
# This is free software, licensed under the Apache License, Version 2.0 .
#
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk

PKG_NAME:=luci-base
PKG_RELEASE:=1

LUCI_TYPE:=mod
LUCI_BASENAME:=base
LUCI_TITLE:=LuCI core libraries
LUCI_DEPENDS:=+lua +luci-lib-nixio +luci-lib-ip +rpcd +libubus-lua +luci-lib-jsonc +liblucihttp-lua +rpcd-mod-file +rpcd-mod-luci +cgi-io

# FIXED PATH TO luci.mk (Adjust as needed)
include $(TOPDIR)/feeds/luci/luci.mk

define Package/$(PKG_NAME)/conffiles
/etc/luci-uploads
/etc/config/luci
/etc/config/ucitrack
endef

define Host/Compile
	$(MAKE) -C src/ clean po2lmo jsmin
endef

define Host/Install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) src/po2lmo $(1)/bin/po2lmo
	$(INSTALL_BIN) src/jsmin $(1)/bin/jsmin
endef

define Package/$(PKG_NAME)/install
	$(call BuildPackage/luci/install/template)
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,$(PKG_NAME)))

# call BuildPackage - OpenWrt buildroot signature
