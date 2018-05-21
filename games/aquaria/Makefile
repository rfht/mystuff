# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - needs instructions on getting game data
# - add lua and sdl1.2 dependencies
# - check that bundled libs of lua, libogg, libvorbis are not used
# AQUARIA_DEFAULT_DATA_DIR:STRING=
# AQUARIA_DEMO_BUILD:BOOL=OFF
# AQUARIA_EXTRA_DATA_DIR:STRING=
# right now needs AQUARIA_DATA_PATH to be set
# troubleshoot keyboard controls - right now it only recognizes the left mouse button, and I can't even open up the menu

COMMENT =	open-source fork of aquaria, an underwater action game

V = 20160619
DISTNAME =	aquaria-${V}
#PKGNAME =	???

GH_ACCOUNT =	AquariaOSE
GH_PROJECT =	Aquaria
GH_COMMIT =	84366ad533fb42d00f6645052b9e56f693b81a2c

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	games

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#GPLv2
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =	devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
LIB_DEPENDS =	audio/openal \
		audio/libvorbis \
		audio/libogg \
		devel/sdl2 \
		graphics/png \
		graphics/ftgl \
		textproc/tinyxml2

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
CONFIGURE_ARGS =	-DAQUARIA_INTERNAL_FREETYPE=OFF \
			-DAQUARIA_INTERNAL_LUA=OFF \
			-DAQUARIA_INTERNAL_OGGVORBIS=OFF \
			-DAQUARIA_INTERNAL_PNG=OFF \
			-DAQUARIA_INTERNAL_ZLIB=OFF \
			-DAQUARIA_USE_SDL2=ON \
			-DAQUARIA_INTERNAL_FTGL=OFF \
			-DAQUARIA_INTERNAL_FTGL="~/.Aquaria/data"
#CONFIGURE_ENV =	???

#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes

#
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

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/aquaria ${PREFIX}/bin	

.include <bsd.port.mk>
