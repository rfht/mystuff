# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	portable, linkable version of unbound

V =		1.7.1
DISTNAME =	unbound-${V}
PKGNAME =	libunbound-${V}

SHARED_LIBS +=  unbound                   4.0 # 7.9

CATEGORIES =	net
HOMEPAGE =	https://www.unbound.net
MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# BSD-3-Clause
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += crypto pthread ssl

MASTER_SITES =	https://www.unbound.net/downloads/

CONFIGURE_ENV =	ac_cv_prog_doxygen=false

SEPARATE_BUILD =	Yes
CONFIGURE_STYLE =	gnu

ALL_TARGET =		lib
INSTALL_TARGET =	install-lib

do-test:
	env -i ${ALL_TEST_ENV} ${MAKE_PROGRAM} ${ALL_TEST_FLAGS} \
		-C ${WRKBUILD} tests
	cd ${WRKSRC} && ${WRKBUILD}/unittest

.include <bsd.port.mk>
