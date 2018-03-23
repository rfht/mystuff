# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	library for communicating with USB and Bluetooth HID devices

V =	20160128
DISTNAME =	hidapi-${V}
#PKGNAME =	???

GH_ACCOUNT =	signal11
GH_PROJECT =	hidapi
#GH_TAGNAME =	1.0
GH_COMMIT =	a6a622ffb680c55da0de787ff93b80280498330f

#SHARED_LIBS =	???

CATEGORIES =	comms


#MAINTAINER =		???

# GPLv3, BSD-style, or more liberal original HIDAPI license
# chosen at the discretion of the user of HIDAPI
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MASTER_SITES =		???
#MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=subdir/}
#MASTER_SITES =		${MASTER_SITE_foo:=subdir/}

#EXTRACT_SUFX =		.tar.bz2

#MODULES =		???
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
LIB_DEPENDS =		devel/libusb1
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
#USE_GROFF =		Yes
CONFIGURE_STYLE =	gnu
#CONFIGURE_SCRIPT =	??? (if other than configure)
#CONFIGURE_ARGS =	???
#CONFIGURE_ENV =	???

# for gnu stuff
AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15
# config.guess and others are copied here
#MODGNU_CONFIG_GUESS_DIRS = ??? (defaults to ${WRKSRC})

#TEST_IS_INTERACTIVE =		Yes

#NO_BUILD =		Yes
#NO_TEST =		Yes

# Overrides for default values
#
#CFLAGS =		???
#LDFLAGS =		???
#MAKE_FILE =		???
#PKG_ARCH =		??? (* for arch-independent packages)
#WRKDIST =		??? if other than ${WRKDIR}/${DISTNAME}
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

.include <bsd.port.mk>
