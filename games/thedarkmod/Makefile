# $OpenBSD: Makefile.template,v 1.76 2017/02/25 16:04:20 danj Exp $

# TODO:
# - fix
# - add license
# - fix COMMENT
# - Error: O3 not found in regular CPPFLAGS, not removing this one.
# - add CC and CXX to CONFIGURE_ARGS instead of _ENV?
# - is devel/boost BDEP or LDEP?
# - -m32 -O3 -march=pentium3 -ffast-math -> keep or nuke?
# - several errors of not finding a file are shown during build, but don't abort
#   the build
# - can't find AL/al.h, but doesn't stop build
# - https available
# - add BUILD="release" to MODSCONS_FLAGS?

COMMENT =	stealth game

DISTNAME =	thedarkmod.2.05

CATEGORIES =	games

HOMEPAGE =	http://www.thedarkmod.com

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

PERMIT_PACKAGE_CDROM =	Yes
#PERMIT_PACKAGE_FTP =	Yes | Reason if No
#PERMIT_DISTFILES_FTP =	Yes | Reason if No

#WANTLIB =		???

MASTER_SITES =		http://www.thedarkmod.com/sources/

EXTRACT_SUFX =		.src.7z

MODULES =		devel/scons
BUILD_DEPENDS =		archivers/p7zip \
			devel/boost
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???

#MAKE_FLAGS =		-std=c++11

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
# CXXFLAGS =		-I${X11BASE}/include -I${LOCALBASE}/include
# CONFIGURE_ENV =		CC="${CC}" CXX="${CXX}"

CXXFLAGS+=	-I/usr/local/include
MODSCONS_ENV =	CC=${CC} \
		CFLAGS=${CFLAGS} \
		CPPFLAGS="-I${LOCALBASE}/include" \
		CXX=${CXX} \
		CXXFLAGS=${CXXFLAGS} \
		LINKFLAGS=${LDFLAGS} \
		CPPPATH='/usr/local/include'

MODSCONS_FLAGS =	ALSA=0 \
			BUILD_GAMEPAK="1" \
			--debug=explain

do-extract:
	7z x ${DISTDIR}/${DISTFILES} -o${WRKSRC}

.include <bsd.port.mk>
