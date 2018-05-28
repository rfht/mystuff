# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# - review license situation
# - order of Makefile okay? esp. COMPILER

COMMENT =	fork of the DOSBox project

DISTNAME =	dosbox-x-windows-20180316

GH_ACCOUNT =	joncampbell123
GH_PROJECT =	dosbox-x
GH_TAGNAME =	dosbox-x-windows-20180316-2157

CATEGORIES =	emulators

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# Needs double-checking of licenses. States GPLv2, but there are reports of other licenses of
# modules pulled into this project that are proprietary
PERMIT_PACKAGE_CDROM =	No
PERMIT_PACKAGE_FTP =	No
PERMIT_DISTFILES_FTP = 	No

WANTLIB += ${COMPILER_LIBCXX} X11 c m pcap z SDL2 png

COMPILER =	base-clang ports-gcc

#MODULES =		???
BUILD_DEPENDS=          ${MODGNU_AUTOCONF_DEPENDS} \
                        ${MODGNU_AUTOMAKE_DEPENDS}
#RUN_DEPENDS =		???
LIB_DEPENDS =		devel/sdl2 \
			graphics/png

SEPARATE_BUILD =	Yes

USE_GMAKE =		Yes

CONFIGURE_STYLE =	gnu

# probably needs CONFIGURE_ARGS += --disable-dynamic-core

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

post-patch:
	cd ${WRKSRC} && env AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} ./autogen.sh

.include <bsd.port.mk>
