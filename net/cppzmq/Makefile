# $OpenBSD: Makefile,v 1.29 2018/04/02 13:28:58 jasper Exp $

# TODO:
# - check correct order of Makefile
# - double-check license info
# - check if there's a test target/do-test

COMMENT =		C++ bindings for zeromq

V =			4.2.2
DISTNAME =		cppzmq-${V}

#SHARED_LIBS +=  zmq                  4.2      # 6.3

GH_ACCOUNT =	zeromq
GH_PROJECT =	cppzmq
GH_TAGNAME =	v${V}

CATEGORIES =	net

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =	???

MODULES =	devel/cmake
#LIB_DEPENDS =		security/libsodium
LIB_DEPENDS =	net/zeromq

#USE_GMAKE =		Yes

#CONFIGURE_STYLE =	gnu
#CONFIGURE_ARGS =	--disable-Werror
# XXX: verify tweetnacl (the default) uses proper randomness before using it
#CONFIGURE_ARGS +=	--with-libsodium

# XXX libsodium: https://github.com/jedisct1/libsodium/pull/104
#CONFIGURE_ENV =		CXXFLAGS="-Wno-long-long ${CXXFLAGS}"

.include <bsd.port.mk>
