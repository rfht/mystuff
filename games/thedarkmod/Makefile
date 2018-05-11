# $OpenBSD: Makefile.template,v 1.76 2017/02/25 16:04:20 danj Exp $

# TODO:
# - fix
# - add license
# - fix COMMENT

COMMENT =	stealth game

DISTNAME =	thedarkmod.2.05

CATEGORIES =	games

#HOMEPAGE =	???	URL

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
#MAKE_ENV =		CXXFLAGS=${CXXFLAGS}
MAKE_ENV =              X11BASE="${X11BASE}" \
			CC="${CC}" \
			CXX="${CXX}" \
			CFLAGS="${CFLAGS}" \
			CXXFLAGS="${CXXFLAGS}"

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
# Programs that require GNU libtool to build instead of the OpenBSD one
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	-I/usr/X11R6/include
#CXXFLAGS =		"-I/usr/X11R6/include"
CONFIGURE_ENV =		CC="${CC}" CXX="${CXX}"

#MODSCONS_FLAGS =	BUILD="release" BUILD_GAMEPAK="1"

do-extract:
	7z x ${DISTDIR}/${DISTFILES} -o${WRKSRC}

post-extract:
	rm -rf ${WRKSRC}/include/boost

.include <bsd.port.mk>
