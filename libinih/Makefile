include $(TOPDIR)/rules.mk

PKG_NAME:=libinih
PKG_VERSION:=56
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=inih-r$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/benhoyt/inih/tar.gz/r$(PKG_VERSION)?
PKG_HASH:=4f2ba6bd122d30281a8c7a4d5723b7af90b56aa828c0e88256d7fceda03a491a

PKG_MAINTAINER:=sbwml <admin@cooluc.com>
PKG_LICENSE:=BSD
PKG_LICENSE_FILES:=LICENSE.txt

PKG_INSTALL:=1
PKG_BUILD_DIR:=$(BUILD_DIR)/inih-r$(PKG_VERSION)
HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/inih-r$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/meson.mk

define Package/libinih
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=inih (INI Not Invented Here)
  URL:=https://github.com/benhoyt/inih
  DEPENDS:=+libstdcpp
endef

define Package/libinih/description
  Simple .INI file parser in C, good for embedded systems
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define Package/libinih/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libinih.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libinih))
$(eval $(call HostBuild))
