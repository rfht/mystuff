# $OpenBSD: Makefile.template,v 1.76 2017/02/25 16:04:20 danj Exp $

COMMENT =	stealth game

DISTNAME =	thedarkmod.2.05

CATEGORIES =	games

#HOMEPAGE =	???	URL

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#PERMIT_PACKAGE_CDROM =	Yes | Reason if No
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
#TEST_DEPENDS =		???

MAKE_FLAGS =		-std=c++14
#MAKE_ENV =		CXXFLAGS=${CXXFLAGS}
MAKE_ENV =              X11BASE="${X11BASE}" \
			CC="${CC}" \
			CXX="${CXX}" \
			CFLAGS="${CFLAGS}" \
			CXXFLAGS="${CXXFLAGS}"

#FAKE_FLAGS =		???
#TEST_FLAGS =		???

# build/configuration variables
#
#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
#USE_GROFF =		Yes
# Programs that require GNU libtool to build instead of the OpenBSD one
# should use this option. Add a comment explaining why. Don't use this if
# a port requires libtool's .m4 files but otherwise can use OpenBSD libtool,
# in that case use "BUILD_DEPENDS=devel/libtool" instead.
#USE_LIBTOOL=		gnu
# Set CONFIGURE_STYLE to value corresponding to some standard configuration
# 	  perl [modbuild]: perl's MakeMaker Makefile.PL (modbuild: perl's
#	  Module::Build Build.PL)
# 	  gnu [autoconf] [old] [dest]: gnu style configure (old: no
# 	  sysconfdir), (dest: add DESTDIR, does not handle it),
# 	  (autoconf: needed by port, implies gnu)
# 	XXX: cygnus products do NOT use autoconf for making the main
# 		configure from configure.in
# 	  imake [noman]: port uses imake for configuration.
#	  (noman: no man page installation)
# 	  simple: port has its own configure script
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	-I/usr/X11R6/include
#CXXFLAGS =		"-I/usr/X11R6/include"
#CONFIGURE_ENV =		CXXFLAGS=${CXXFLAGS}

#MODSCONS_FLAGS =	BUILD="release" BUILD_GAMEPAK="1"

do-extract:
	7z x ${DISTDIR}/${DISTFILES} -o${WRKSRC}

post-extract:
	rm -rf ${WRKSRC}/include/boost

.include <bsd.port.mk>
