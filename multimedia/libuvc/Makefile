# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - seems that -DBUILD_EXAMPLE and -DBUILD_TEST don't work.
#   test apparently just needs to be uncommented in CMakeLists.txt
#   example may not be available
# - add jpeg to LDEP/BDEP?
# - the shared library isn't properly set up - no version number extension, not recognized by make package/plist
#   as shared object
# - depends on opencv for test

COMMENT =	library for USB video devices


# use GH_TAGNAME = 0.0.6 (Sept 2017), or recent commit? 77b43d618e71698f52f7beb88c4b99b5f018259b
V =		20170822
DISTNAME =	libuvc-${V}
PKGNAME =	libuvc-0.0.6.${V}

GH_ACCOUNT =	ktossell
GH_PROJECT =	libuvc
# GH_TAGNAME =	v${V}
GH_COMMIT =	77b43d618e71698f52f7beb88c4b99b5f018259b

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
SHARED_LIBS =		libuvc		0.0	# 0.0.6

CATEGORIES =	multimedia

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# BSD license
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =	devel/cmake
LIB_DEPENDS =	devel/libusb1

CONFIGURE_ARGS =	-DBUILD_EXAMPLE=ON \
			-DBUILD_TEST=ON

#TEST_IS_INTERACTIVE =		Yes

#NO_TEST =		Yes

.include <bsd.port.mk>
