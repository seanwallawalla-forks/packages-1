#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=expat
PKG_VERSION:=2.4.6
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@SF/expat
PKG_HASH:=de55794b7a9bc214852fdc075beaaecd854efe1361597e6268ee87946951289b

PKG_MAINTAINER:=Ted Hess <thess@kitschensync.net>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:libexpat:expat

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libexpat
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=An XML parsing library
  URL:=https://libexpat.github.io/
endef

define Package/libexpat/description
 A fast, non-validating, stream-oriented XML parsing library.
endef

CMAKE_OPTIONS += \
	-DDOCBOOK_TO_MAN=OFF \
	-DEXPAT_BUILD_TOOLS=OFF \
	-DEXPAT_BUILD_EXAMPLES=OFF \
	-DEXPAT_BUILD_TESTS=OFF \
	-DEXPAT_BUILD_DOCS=OFF \
	-DEXPAT_WITH_LIBBSD=OFF \
	-DEXPAT_ENABLE_INSTALL=ON \
	-DEXPAT_DTD=OFF \
	-DEXPAT_NS=OFF \
	-DEXPAT_DEV_URANDOM=OFF

define Package/libexpat/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libexpat.so.* $(1)/usr/lib/
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,libexpat))
