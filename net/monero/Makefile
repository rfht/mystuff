# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - source and binary distributions must retain copyright notice
# - INSTALL COPYRIGHT NOTICE
# - double check that this is really BSD 3-Clause
# - compare submodule use to reference ppsspp
# - submit net/libunbound before this port
# - Absolute name forbidden: /etc/unbound/unbound.conf at /usr/libdata/perl5/OpenBSD/PackingElement.pm line 217, <$fh> line 52.
#   *** Error 25 in mystuff/net/libunbound (/usr/ports/infrastructure/mk/bsd.port.mk:2880 'print-plist': @/usr/sbin/pkg_create -m -n -q   -DHIST...)
#   *** Error 1 in /usr/ports (infrastructure/mk/bsd.port.subdir.mk:147 'print-plist')
# - should monerod get an rc.d script? how?
# - install utils/conf/monerod.conf in examples? (use ${EXAMPLEDIR})
# - 'monerod --help' mentions ~/.bitmonero/bitmonero.conf
# - check licenses of 3rdparty/external modules
# - mention achieved HR of 90 with 6 threads on i7-6820HQ which isn't great

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
WANTLIB += ssl unbound zmq

CPPZMQ =	4.2.2

MASTER_SITES0 =	https://github.com/zeromq/cppzmq/archive/

DISTFILES =	monero-${V}${EXTRACT_SUFX} \
		v${CPPZMQ}.tar.gz:0

MODULES =	devel/cmake
BUILD_DEPENDS =	devel/boost
LIB_DEPENDS =	devel/boost \
		net/libunbound \
		net/miniupnp/miniupnpc \
		net/zeromq \
		security/pcsc-lite

CONFIGURE_ARGS =	-DBUILD_DOCUMENTATION=OFF

NO_TEST =	Yes

post-extract:
	ln -s ${WRKDIR}/cppzmq-${CPPZMQ}/zmq.hpp ${WRKSRC}/src

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/monero
	${INSTALL_DATA} ${WRKSRC}/LICENSE \
		${PREFIX}/share/doc/monero/LICENSE-monero
	${INSTALL_DATA} ${WRKDIR}/cppzmq-${CPPZMQ}/LICENSE \
		${PREFIX}/share/doc/monero/LICENSE-cppzmq

.include <bsd.port.mk>
