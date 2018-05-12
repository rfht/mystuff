# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - source and binary distributions must retain copyright notice
# - INSTALL COPYRIGHT NOTICE
# - double check that this is really BSD 3-Clause
# - should monerod get an rc.d script? how?
# - install utils/conf/monerod.conf in examples? (use ${EXAMPLEDIR})
# - 'monerod --help' mentions ~/.bitmonero/bitmonero.conf
# - check licenses of 3rdparty/external modules
# - what about others in external? (boost/archive, db_drivers, easylogging++,
#   rapidjson)
# - double-check configure stage
# - now installs lib/libunbound.a
# - performance may be better with statically compiled unbound
# - MAX HASHRATE ACHIEVED: 116 (7 threads), seem to be averaging 105-110
#   at 55-60W, better even with 4 threads, mostly HR 115-117, up to 132

COMMENT =	client for Monero cryptocurrency

V = 0.12.0.0
DISTNAME =	monero-${V}{v${V}}
PKGNAME =	monero-${V}

GH_ACCOUNT =	monero-project
GH_PROJECT =	monero
GH_TAGNAME =	v${V}

CATEGORIES =	net

MAINTAINER =	Thomas Frohwein <frohwein@fastmail.com>

#BSD 3-Clause
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} boost_chrono-mt boost_date_time-mt
WANTLIB += boost_filesystem-mt boost_program_options-mt boost_regex-mt
WANTLIB += boost_serialization-mt boost_system-mt boost_thread-mt
WANTLIB += c crypto curses m miniupnpc pcsclite readline sodium
WANTLIB += ssl zmq

CPPZMQ =	4.2.2
UNBOUND =	193bdc4ee3fe2b0d17e547e86512528c2614483a

MASTER_SITES0 =	https://github.com/zeromq/cppzmq/archive/
MASTER_SITES1 =	https://github.com/monero-project/unbound/archive/

DISTFILES =	monero-${V}${EXTRACT_SUFX} \
		v${CPPZMQ}.tar.gz:0 \
		${UNBOUND}.tar.gz:1

MODULES =	devel/cmake
BUILD_DEPENDS =	devel/boost
LIB_DEPENDS =	devel/boost \
		net/miniupnp/miniupnpc \
		net/zeromq \
		security/pcsc-lite

CONFIGURE_ARGS =	-DBUILD_DOCUMENTATION=OFF \
			-DINSTALL_VENDORED_LIBUNBOUND=ON

NO_TEST =	Yes

post-extract:
	rmdir	${WRKSRC}/external/unbound
	ln -s	${WRKDIR}/unbound-${UNBOUND} ${WRKSRC}/external/unbound
	ln -s	${WRKDIR}/cppzmq-${CPPZMQ}/zmq.hpp ${WRKSRC}/src

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/monero
	${INSTALL_DATA} ${WRKSRC}/LICENSE \
		${PREFIX}/share/doc/monero/LICENSE-monero
	${INSTALL_DATA} ${WRKDIR}/cppzmq-${CPPZMQ}/LICENSE \
		${PREFIX}/share/doc/monero/LICENSE-cppzmq

.include <bsd.port.mk>
