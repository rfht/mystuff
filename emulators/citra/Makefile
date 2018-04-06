# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	nintendo 3DS emulator

V=	0.20180404
DISTNAME =	citra-${V}

# main repo: citra-emu
# experimental repo with some performance improvements: Jhon591
GH_ACCOUNT =	Jhon591
GH_PROJECT =	citra
GH_COMMIT =	94c39c86606f5f00cd5ca77bcae6b01b1c4190a8

#SHARED_LIBS =	???

CATEGORIES =	emulators

#HOMEPAGE =	???	URL

MAINTAINER =		Thomas Frohwein <frohwein@ymail.com>

# !! DOUBLE CHECK LICENSE!!
# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =		devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
#USE_GROFF =		Yes
#USE_LIBTOOL=		gnu
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	-DCMAKE_PREFIX_PATH=/usr/local/lib/qt5/cmake/Qt5/ \
			-DENABLE_QT=OFF
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
