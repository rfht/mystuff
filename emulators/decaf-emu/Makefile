# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - likely needs USE_WXNEEDED
# - double-check license
# - add submodules (in folder 'libraries')
# - textproc/pugixml could maybe run with port

COMMENT =	Wii U emulator

V =		20180217
HASH =		593cb873
DISTNAME =	decaf-emu-${V}-${HASH}
#PKGNAME =	???

GH_ACCOUNT =	decaf-emu
GH_PROJECT =	decaf-emu
#GH_TAGNAME =	1.0
GH_COMMIT =	593cb8737ea0c049fc69a84a58a729c058d345a7

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	emulators

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

LIBBINREC =	84f37f0d21dc828cc5010e7bdf6713db283299f2
FMT =		7a9c1ba190cb61b00f7ffac628ff30c9c0a9e076
GLBINDING =	98d3695be4311770fc6cc99b30ad17073daf0587
ADDRLIB =	d30a77f63a3bfbb91d580ed21cc82369e63d8c5c
IMGUI =		6384eee34f08cb7eab8d835043e1738e4adcdf75

MASTER_SITES0 =	https://github.com/decaf-emu/libbinrec/archive/
MASTER_SITES1 =	https://github.com/fmtlib/fmt/archive/
MASTER_SITES2 =	https://github.com/cginternals/glbinding/archive/
MASTER_SITES3 =	https://github.com/decaf-emu/addrlib/archive/
MASTER_SITES4 =	https://github.com/ocornut/imgui/archive/

DISTFILES =	${DISTNAME}${EXTRACT_SUFX} \
		${LIBBINREC}.tar.gz:0 \
		${FMT}.tar.gz:1 \
		${GLBINDING}.tar.gz:2 \
		${ADDRLIB}.tar.gz:3 \
		${IMGUI}.tar.gz:4

MODULES =	devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???
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
#CONFIGURE_ARGS =	???
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

post-extract:
	rmdir	${WRKSRC}/libraries/libbinrec \
		${WRKSRC}/libraries/fmt \
		${WRKSRC}/libraries/glbinding \
		${WRKSRC}/libraries/addrlib \
		${WRKSRC}/libraries/imgui
	ln -s ${WRKDIR}/libbinrec-${LIBBINREC} ${WRKSRC}/libraries/libbinrec
	ln -s ${WRKDIR}/fmt-${FMT} ${WRKSRC}/libraries/fmt
	ln -s ${WRKDIR}/glbinding-${GLBINDING} ${WRKSRC}/libraries/glbinding
	ln -s ${WRKDIR}/addrlib-${ADDRLIB} ${WRKSRC}/libraries/addrlib
	ln -s ${WRKDIR}/imgui-${IMGUI} ${WRKSRC}/libraries/imgui

.include <bsd.port.mk>
