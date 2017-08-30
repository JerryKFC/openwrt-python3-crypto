#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pycrypto
PKG_VERSION:=2.6.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://ftp.dlitz.net/pub/dlitz/crypto/pycrypto/
PKG_MD5SUM:=55a61a054aa66812daf5161a0d5d7eda
PKG_BUILD_DIR:=$(BUILD_DIR)/pycrypto-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-crypto
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=The Python Cryptography Toolkit
	URL:=https://www.dlitz.net/software/pycrypto/
	DEPENDS:=+python3
endef

define Package/python3-crypto/description
A collection of both secure hash functions (such as MD5 and SHA),
and various encryption algorithms (AES, DES, IDEA, RSA, ElGamal, etc.).
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="$(PKG_INSTALL_DIR)/usr")
endef

define Package/python3-crypto/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)
	$(CP) $(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* $(1)$(PYTHON3_PKG_DIR)
endef

$(eval $(call PyPackage,python3-crypto))
$(eval $(call BuildPackage,python3-crypto))
