#
# Copyright (C) 2010-2023 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=myautocore
PKG_VERSION:=2
PKG_RELEASE:=5

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/target.mk

define Package/myautocore-arm
  TITLE:=Arm auto core loadbalance script.
  MAINTAINER:=CN_SZTL
  DEPENDS:=@(arm||aarch64||TARGET_bcm27xx||TARGET_bcm53xx||TARGET_ipq40xx||TARGET_ipq806x||TARGET_ipq807x||TARGET_mvebu||TARGET_rockchip||TARGET_armvirt) \
    +TARGET_bcm27xx:bcm27xx-userland \
	+TARGET_bcm53xx:nvram +ethtool
  VARIANT:=arm
endef

define Package/myautocore-x86
  TITLE:=x86/x64 auto core loadbalance script.
  DEPENDS:=@TARGET_x86 +bc +ethtool +lm-sensors +pciutils
  VARIANT:=x86
endef

define Package/myautocore-arm/description
  A luci autoconfig hotplug script.
endef

define Package/myautocore-x86/description
  A usb autoconfig hotplug script.
endef

define Build/Compile
endef

define Package/myautocore-arm/install
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/arm/index.htm $(1)/etc/index.htm
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/60-autocore-reload-rpcd $(1)/etc/uci-defaults/
	$(INSTALL_BIN) ./files/arm/090-cover-index_htm $(1)/etc/uci-defaults/
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) ./files/arm/sbin/cpuinfo $(1)/sbin/cpuinfo
	$(INSTALL_BIN) ./files/arm/sbin/ethinfo $(1)/sbin/ethinfo
	$(INSTALL_BIN) ./files/arm/sbin/usage $(1)/sbin/usage
ifneq ($(filter ipq% %filogic qualcommax%, $(CONFIG_TARGET_BOARD)),)
	$(INSTALL_BIN) ./files/arm/sbin/tempinfo $(1)/sbin/tempinfo
endif
	$(INSTALL_DIR) $(1)/usr/share/rpcd/acl.d
	$(CP) ./files/luci-mod-status-autocore.json $(1)/usr/share/rpcd/acl.d/
endef

define Package/myautocore-x86/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/x86/autocore $(1)/etc/init.d/autocore
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/x86/index.htm $(1)/etc/index.htm
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/60-autocore-reload-rpcd $(1)/etc/uci-defaults/
	$(INSTALL_DIR) $(1)/sbin
	$(CP) ./files/x86/sbin/* $(1)/sbin
	$(INSTALL_DIR) $(1)/usr/share/rpcd/acl.d
	$(CP) ./files/luci-mod-status-autocore.json $(1)/usr/share/rpcd/acl.d/
endef

$(eval $(call BuildPackage,myautocore-arm))
$(eval $(call BuildPackage,myautocore-x86))
