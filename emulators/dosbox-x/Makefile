# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# - double-check that patch comments are still correct after changes
# - review license situation
# - order of Makefile okay? esp. COMPILER
# - MASTER_SITES line too long - can be wrapped?
# - make sure dosbox-x honors CFLAGS, CPPFLAGS, LDFLAGS
# - per README ffmpeg and libav support required ???
# - SDL2 may not be mature enough, e.g. for output=opengl etc
# - only takes the *bundled* SDL1 now, and building that is difficult

COMMENT =	fork of the DOSBox project

V =		0.82.7
DISTNAME =	dosbox-x-windows-v${V}
PKGNAME =	dosbox-x-${V}

GH_ACCOUNT =	joncampbell123
GH_PROJECT =	dosbox-x
GH_TAGNAME =	dosbox-x-windows-v${V}

CATEGORIES =	emulators

MAINTAINER =	Thomas Frohwein <frohwein@fastmail.com>

# Needs double-checking of licenses. States GPLv2, but there are reports of other licenses of
# modules pulled into this project that are proprietary
PERMIT_PACKAGE_CDROM =	No
PERMIT_PACKAGE_FTP =	No
PERMIT_DISTFILES_FTP = 	No

WANTLIB += ${COMPILER_LIBCXX} SDL2 X11 c m pcap png xkbfile z

# C++11
COMPILER =		base-clang ports-gcc

BUILD_DEPENDS=          ${MODGNU_AUTOCONF_DEPENDS} \
                        ${MODGNU_AUTOMAKE_DEPENDS}
LIB_DEPENDS =		devel/sdl2 \
			graphics/png

SEPARATE_BUILD =	Yes
USE_GMAKE =		Yes
CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--disable-alsatest \
			--enable-core-inline \
			--disable-debug \
			--enable-avcodec

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

post-patch:
	cd ${WRKSRC} && env AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} ./autogen.sh

pre-build:
	cd ${WRKSRC}/vs2015/sdl && ./build-dosbox.sh

.include <bsd.port.mk>
