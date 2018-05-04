# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - double-check license! esp. 3rdparty!
# - remove unnecessary thirdparty stuff
# - change hardcoded path in patches to LOCALBASE, with SUBST_CMD
# - is SDL_audio.h header from devel/sdl2? or sdl2-mixer?

COMMENT =	mobile platform for pro game developers

V =		1.5.2
#DISTNAME =	???
PKGNAME =	moai-${V}
#PKGNAME-foo =	???	for multi packages

GH_ACCOUNT =	moai
GH_PROJECT =	moai-dev
GH_TAGNAME =	Version-${V}-binary-desktop
#GH_COMMIT =	abab123456789abacafeabab123123b1e4ble4bl

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	games

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# CPALv1.0
PERMIT_PACKAGE_CDROM =	Yes

# "make port-lib-depends-check" can help
#WANTLIB =		???

#MASTER_SITES =		???

#MASTER_SITES0 =

#DISTFILES =		???

MODULES =	devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
LIB_DEPENDS =	devel/sdl2 \
		graphics/freeglut \
		graphics/glew \
		net/curl
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

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
CONFIGURE_ARGS =	-DBUILD_LINUX=TRUE
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
WRKSRC =	${WRKDIST}/cmake
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

.include <bsd.port.mk>
