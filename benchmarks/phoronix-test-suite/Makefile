# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# - double-check license
# - attribution of patch-install-sh to FreeBSD?
# - php as module or BDEP/LDEP/RDEP?
# - check configuration options
# - add replacement for /usr/local with LOCALBASE as in FreeBSD's Makefile
# - GD        The GD library is recommended for improved graph rendering.
# - Bzip2     The bzcompress/bzip2 support can be used for greater file compression.
# - PCNTL     PCNTL is highly recommended as it is required by some tests.
# - CURL      CURL is recommended for an enhanced download experience.
#
# - [NOTICE] Failed To Fetch OpenBenchmarking.org Repository Data: pts 
# - [NOTICE] Failed To Fetch OpenBenchmarking.org Repository Data: system 

COMMENT =	Phoronix automated benchmarking/testing suite

DISTNAME =	phoronix-test-suite-7.8.0
#PKGNAME =	???

#GH_ACCOUNT =	username
#GH_PROJECT =	project
#GH_TAGNAME =	1.0
#GH_COMMIT =	abab123456789abacafeabab123123b1e4ble4bl

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	benchmarks

#HOMEPAGE =	https://www.phoronix-test-suite.com

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MASTER_SITES =		https://www.phoronix-test-suite.com/releases/

MODULES =	lang/php
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
#CONFIGURE_ARGS =	???
#CONFIGURE_ENV =	???

#AUTOCONF_VERSION =	??? (defaults to 2.13)
#AUTOMAKE_VERSION =	??? (defaults to 1.4)
# config.guess and others are copied here
#MODGNU_CONFIG_GUESS_DIRS = ??? (defaults to ${WRKSRC})

#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes

NO_BUILD =		Yes
#NO_TEST =		Yes

#CFLAGS =		???
#LDFLAGS =		???
#MAKE_FILE =		???
#PKG_ARCH =		??? (* for arch-independent packages)
WRKDIST =	${WRKDIR}/phoronix-test-suite
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

do-install:
	(cd ${WRKSRC} && ${CONFIGURE_ARGS} DESTDIR="${STAGEDIR}" ./install-sh ${PREFIX})

.include <bsd.port.mk>
