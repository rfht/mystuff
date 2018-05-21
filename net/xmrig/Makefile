# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - parentheses in COMMENT okay?
# - category net adequate?
# - double check 3rdparty libs
# - seems to depend on www/microhttpd by default
# - seems to depend on devel/libuv
# - need to install license, too?

COMMENT =	Monero (XMR) CPU miner

GH_ACCOUNT =	xmrig
GH_PROJECT =	xmrig
GH_TAGNAME =	v2.6.2

CATEGORIES =	net

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} c m microhttpd uv

MODULES =	devel/cmake
LIB_DEPENDS =	devel/libuv \
		www/libmicrohttpd

NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/xmrig ${PREFIX}/bin

.include <bsd.port.mk>
