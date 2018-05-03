# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - seems that -DBUILD_EXAMPLE and -DBUILD_TEST don't work.
#   test apparently just needs to be uncommented in CMakeLists.txt
#   example may not be available
# - add jpeg to LDEP/BDEP?
# - the shared library isn't properly set up - no version number extension, not recognized by make package/plist
#   as shared object

COMMENT =	library for USB video devices

V =		0.0.6
GH_ACCOUNT =	ktossell
GH_PROJECT =	libuvc
GH_TAGNAME =	v${V}

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
SHARED_LIBS =		libuvc		0.0	# 0.0.6

CATEGORIES =	multimedia

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# BSD license
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =	devel/cmake
LIB_DEPENDS =	devel/libusb1

#TEST_IS_INTERACTIVE =		Yes

#NO_TEST =		Yes

.include <bsd.port.mk>
