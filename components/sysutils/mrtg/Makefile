#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2013 Alexander Pyhalov.  All rights reserved.
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= mrtg
COMPONENT_VERSION= 2.17.4
COMPONENT_REVISION= 1
COMPONENT_SUMMARY= mrtg - The Multi Router Traffic Grapher
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:5efa7fae8040159208472e5f889be5b41d8c8a2ea6b31616f0f75cc7f48d2365
COMPONENT_ARCHIVE_URL= \
  http://oss.oetiker.ch/mrtg/pub/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = http://oss.oetiker.ch/mrtg/

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

COMPONENT_PRE_CONFIGURE_ACTION =        ($(CLONEY) $(SOURCE_DIR) $(@D))

CONFIGURE_SCRIPT=       $(@D)/configure
CONFIGURE_OPTIONS+=	--with-gd-lib=/usr/lib
CONFIGURE_OPTIONS+=	--with-gd-inc=/usr/include/gd2


build: $(BUILD_32)

install: $(INSTALL_32)

test: $(NO_TESTS)

REQUIRED_PACKAGES += image/rrdtool
REQUIRED_PACKAGES += library/gd
REQUIRED_PACKAGES += runtime/perl-522
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/math
