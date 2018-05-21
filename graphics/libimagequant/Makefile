# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - bug upstream about stable release assets
# - review license (GPLv3 + copyright notice which is BSD-like)
# - fix license comment
# - symlink to .so.0.0 okay?

COMMENT =	palette quantization library

#DISTNAME =	???
#PKGNAME =	???

GH_ACCOUNT =	ImageOptim
GH_PROJECT =	libimagequant
GH_TAGNAME =	2.11.10
#GH_COMMIT =	abab123456789abacafeabab123123b1e4ble4bl

SHARED_LIBS =	imagequant	0.0	# version 2.11.10

CATEGORIES =	graphics

#HOMEPAGE =	???	URL

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# GPLv3 + like 2-clause BSD
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

#MASTER_SITES =		???

#MODULES =		???
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???
#TEST_DEPENDS =		???

MAKE_FLAGS =	SOVER=${LIBimagequant_VERSION}
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
USE_GMAKE =		Yes
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
CONFIGURE_ARGS =	CC=${CC} \
			CFLAGS=${CFLAGS} \
			LDFLAGS=${LDFLAGS}
#CONFIGURE_ENV =	???

#AUTOCONF_VERSION =	??? (defaults to 2.13)
#AUTOMAKE_VERSION =	??? (defaults to 1.4)
# config.guess and others are copied here
#MODGNU_CONFIG_GUESS_DIRS = ??? (defaults to ${WRKSRC})

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

ALL_TARGET =	shared
#INSTALL_TARGET =	???
#TEST_TARGET =		???

.include <bsd.port.mk>
