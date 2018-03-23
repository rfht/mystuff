# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	core libs, applications, and plugins of OSVR platform

V =		20180226
DISTNAME =	osvr-${V}
#PKGNAME =	???

GH_ACCOUNT =	OSVR
GH_PROJECT =	OSVR-Core
#GH_TAGNAME =	1.0
GH_COMMIT =	59405fc1b1a25aea051dfbba0be5171fa19b8b30

#SHARED_LIBS =	???

CATEGORIES =	comms

#MAINTAINER =		???

# Apache License, Version 2.0
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

# DEPS: libfunctionality, jsoncpp, boost >=1.44, opencv, libusb1
MODULES =		devel/cmake>=3.0
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
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
#CONFIGURE_ARGS =	???
#CONFIGURE_ENV =	???

#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes

#NO_BUILD =		Yes
#NO_TEST =		Yes

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
