# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# needs paths to be fixed to be able to run the mods

COMMENT =	free/libre action roleplaying engine

# there's also a sourceforge repo
GH_ACCOUNT =	clintbellanger
GH_PROJECT =	flare-engine
GH_TAGNAME =	v1.0

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	games

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#GPLv3+, CC-BY-SA 3.0+ (default mod + engine translations), SIL (fonts)
#GPLv2 (GNU Unifont)
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} SDL2 SDL2_image SDL2_mixer SDL2_ttf
WANTLIB += c m

MODULES =	devel/cmake
RUN_DEPENDS =	x11/gtk+3,-guic \
		devel/desktop-file-utils
LIB_DEPENDS =	devel/sdl2 \
		devel/sdl2-image \
		devel/sdl2-mixer \
		devel/sdl2-ttf

NO_TEST =		Yes

.include <bsd.port.mk>
