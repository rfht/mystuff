# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - likely needs USE_WXNEEDED
# - double-check license
# - add submodules (in folder 'libraries')
# - textproc/pugixml could maybe run with port
# - take graphics/glbinding from ports (I prepared it)
# - replace hardcoded path in patch with LOCALBASE and SUBST_CMD
# - put -DPLATFORM_POSIX in CONFIGURE_ARGS rather than patch?
# - installs several truetype fonts; double-check stuff like
#   DejaVuSansMono.LICENSE
# - expand DESCR?
# - decaf-cli and decaf-sdl need to be placed in proper bin directory
# - USE_WXNEEDED ??

USE_WXNEEDED =	Yes

COMMENT =	Wii U emulator

V =		20180217
HASH =		593cb873
DISTNAME =	decaf-emu-${V}-${HASH}
PKGNAME =	decaf-emu-${V}

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
ADDRLIB =	d30a77f63a3bfbb91d580ed21cc82369e63d8c5c
IMGUI =		6384eee34f08cb7eab8d835043e1738e4adcdf75
GSL_LITE =	292615c3c2812bdb224843faa41310b30c1e483a
SPDLOG =	813dcbcf637da5ee11a35943382c36c2a04b1bd8
CPPTOML =	6b780c98c767cf1a9f36b06070db8cf07243354f
FIXED_POINT =	7a084e2f54ef7ecff62f58df30f319185b75cebc
EXCMD =		b48dab4954bdc074d7768e38065171441aaff7ce

MASTER_SITES0 =	https://github.com/decaf-emu/libbinrec/archive/
MASTER_SITES1 =	https://github.com/fmtlib/fmt/archive/
MASTER_SITES2 =	https://github.com/decaf-emu/addrlib/archive/
MASTER_SITES3 =	https://github.com/ocornut/imgui/archive/
MASTER_SITES4 =	https://github.com/decaf-emu/gsl-lite/archive/
MASTER_SITES5 =	https://github.com/gabime/spdlog/archive/
MASTER_SITES6 =	https://github.com/skystrife/cpptoml/archive/
MASTER_SITES7 =	https://github.com/johnmcfarlane/fixed_point/archive/
MASTER_SITES8 =	https://github.com/exjam/excmd/archive/

DISTFILES =	${DISTNAME}${EXTRACT_SUFX} \
		${LIBBINREC}.tar.gz:0 \
		${FMT}.tar.gz:1 \
		${ADDRLIB}.tar.gz:2 \
		${IMGUI}.tar.gz:3 \
		${GSL_LITE}.tar.gz:4 \
		${SPDLOG}.tar.gz:5 \
		${CPPTOML}.tar.gz:6 \
		${FIXED_POINT}.tar.gz:7 \
		${EXCMD}.tar.gz:8

MODULES =	devel/cmake
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
LIB_DEPENDS =	graphics/glbinding
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
		${WRKSRC}/libraries/addrlib \
		${WRKSRC}/libraries/imgui \
		${WRKSRC}/libraries/gsl-lite \
		${WRKSRC}/libraries/spdlog \
		${WRKSRC}/libraries/cpptoml \
		${WRKSRC}/libraries/fixed_point \
		${WRKSRC}/libraries/excmd
	ln -s ${WRKDIR}/libbinrec-${LIBBINREC} ${WRKSRC}/libraries/libbinrec
	ln -s ${WRKDIR}/fmt-${FMT} ${WRKSRC}/libraries/fmt
	ln -s ${WRKDIR}/addrlib-${ADDRLIB} ${WRKSRC}/libraries/addrlib
	ln -s ${WRKDIR}/imgui-${IMGUI} ${WRKSRC}/libraries/imgui
	ln -s ${WRKDIR}/gsl-lite-${GSL_LITE} ${WRKSRC}/libraries/gsl-lite
	ln -s ${WRKDIR}/spdlog-${SPDLOG} ${WRKSRC}/libraries/spdlog
	ln -s ${WRKDIR}/cpptoml-${CPPTOML} ${WRKSRC}/libraries/cpptoml
	ln -s ${WRKDIR}/fixed_point-${FIXED_POINT} ${WRKSRC}/libraries/fixed_point
	ln -s ${WRKDIR}/excmd-${EXCMD} ${WRKSRC}/libraries/excmd

.include <bsd.port.mk>
