# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - revise COMMENT?
# - double-check license
# - set configuration to Release instead of Debug?
# - add lua dependency
# - add other dependencies from make configure
# - check log file for shared libs

COMMENT =	desktop engine, display server, multimedia framework

#DISTNAME =	???
#PKGNAME =	???

GH_ACCOUNT =	letoram
GH_PROJECT =	arcan
GH_TAGNAME =	0.5.4.5

SHARED_LIBS +=  arcan_shmif               0.0 # 0.11
SHARED_LIBS +=  arcan_shmif_ext           0.0 # 0.11
SHARED_LIBS +=  arcan_shmif_server        0.0 # 0.11
SHARED_LIBS +=  arcan_tui                 0.0 # 0.11

CATEGORIES =	multimedia

#HOMEPAGE =	???	URL

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# #-clause BSD, GPLv2+, LGPL
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =	devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
LIB_DEPENDS =	audio/openal \
		databases/sqlite3 \
		devel/sdl \
		graphics/png

#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	-DCMAKE_BUILD_TYPE="Debug" \
			-DVIDEO_PLATFORM=sdl \
			-DLUA_INCLUDE_DIR=${LOCALBASE}/include/lua-5.1

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
WRKSRC =		${WRKDIST}/src
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

post-extract:
	echo "#define gl21" > ${WRKSRC}/shmif/arcan_shmif_cfg.h

.include <bsd.port.mk>
