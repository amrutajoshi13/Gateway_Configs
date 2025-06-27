#
# Copyright (C) 2008-2015 The LuCI Team <luci@lists.subsignal.org>
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI core libraries
LUCI_DEPENDS:=+lua +luci-lib-nixio +luci-lib-ip +rpcd +libubus-lua +luci-lib-jsonc +liblucihttp-lua +rpcd-mod-file +rpcd-mod-luci +cgi-io

include ../../luci.mk

define Package/luci-base/conffiles
/etc/config/luci
/etc/config/ucitrack
/etc/luci-uploads
endef

$(eval $(call BuildPackage,luci-base))

# call BuildPackage - OpenWrt buildroot signature
