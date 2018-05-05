# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

USE_WXNEEDED =	Yes

COMMENT =	nintendo 3DS emulator

NIGHTLY =	670
V=		0.0.${NIGHTLY}
PKGNAME =	citra-${V}

GH_ACCOUNT =	citra-emu
GH_PROJECT =	citra-nightly
GH_TAGNAME =	nightly-${NIGHTLY}

CATEGORIES =	emulators

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv2, BSD-2-clause (fmt), LGPL (getopt), MIT (httplib, json, lurlparser),
# "New BSD license" (inih), unlicense/public domain (microprofile),
# BSD-3-clause (nihstro), LGPLv2.1 (soundtouch), BSD-style (xbyak)
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} Qt5Core Qt5Gui Qt5OpenGL Qt5Widgets
WANTLIB += SDL2 c cryptopp enet iconv m

FMT =		5859e58ba17073cf1c16536205450528f3530df0
NIHSTRO =	fd69de1a1b960ec296cc67d32257b0f9e2d89ac6
DYNARMIC =	d1d4705364031512cb89333aebc00b8d75a2f732
INIH =		56edbbbef9ba432521442ee47ba7d1c8de37e63d
XBYAK =		c5da3778e7f84013fe8c26fcf18a67881bd1e825
SOUNDTOUCH =	019d2089bbadf70d73ba85aa8ea51490b071262c

MASTER_SITES0 = https://github.com/fmtlib/fmt/archive/
MASTER_SITES1 =	https://github.com/neobrain/nihstro/archive/
MASTER_SITES2 =	https://github.com/MerryMage/dynarmic/archive/
MASTER_SITES3 =	https://github.com/benhoyt/inih/archive/
MASTER_SITES4 =	https://github.com/herumi/xbyak/archive/
MASTER_SITES5 =	https://github.com/citra-emu/ext-soundtouch/archive/

DISTFILES =	${DISTNAME}${EXTRACT_SUFX} \
		${FMT}.tar.gz:0 \
		${NIHSTRO}.tar.gz:1 \
		${DYNARMIC}.tar.gz:2 \
		${INIH}.tar.gz:3 \
		${XBYAK}.tar.gz:4 \
		${SOUNDTOUCH}.tar.gz:5

MODULES =	devel/cmake \
		x11/qt5
BUILD_DEPENDS =	devel/catch2
RUN_DEPENDS =	devel/desktop-file-utils \
		misc/shared-mime-info \
		x11/gtk+3,-guic
LIB_DEPENDS =	devel/cryptopp \
		devel/sdl2 \
		net/enet

CONFIGURE_ARGS =	-DCMAKE_CXX_FLAGS="-I${LOCALBASE}/include ${CXXFLAGS}" \
			-DCMAKE_PREFIX_PATH="-I${LOCALBASE}/lib/qt5/cmake/Qt5/" \
			-DENABLE_WEB_SERVICE=OFF

post-extract:
	rmdir	${WRKSRC}/externals/fmt \
		${WRKSRC}/externals/nihstro \
		${WRKSRC}/externals/dynarmic \
		${WRKSRC}/externals/inih/inih \
		${WRKSRC}/externals/xbyak \
		${WRKSRC}/externals/soundtouch
	ln -s ${WRKDIR}/fmt-${FMT} ${WRKSRC}/externals/fmt
	ln -s ${WRKDIR}/nihstro-${NIHSTRO} ${WRKSRC}/externals/nihstro
	ln -s ${WRKDIR}/dynarmic-${DYNARMIC} ${WRKSRC}/externals/dynarmic
	ln -s ${WRKDIR}/inih-${INIH} ${WRKSRC}/externals/inih/inih
	ln -s ${WRKDIR}/xbyak-${XBYAK} ${WRKSRC}/externals/xbyak
	ln -s ${WRKDIR}/ext-soundtouch-${SOUNDTOUCH} ${WRKSRC}/externals/soundtouch

do-test:
	cd ${WRKBUILD}/src/tests && ./tests

.include <bsd.port.arch.mk>

.if ${PROPERTIES:Mclang}
BUILD_DEPENDS+=	devel/llvm
.endif

.include <bsd.port.mk>
