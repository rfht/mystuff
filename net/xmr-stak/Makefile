# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - double check licenses, esp. 3rdparty
# - mention share that goes to the dev by default (2% set during compile time)
# - can OpenCL be enabled??
# - can/should hwloc be enabled? https://github.com/open-mpi/hwloc
# - uses std=c++11 -> need COMPILER = base-clang ports-gcc ??
# - install license or other stuff along with the binary?
# - fix trailing whitespace in Makefile
# - ISSUE: [2018-05-09 10:39:55] : WARNING: thread pinning is not supported under OPENBSD.
#          Abort trap (core dumped)

COMMENT =	unified all-in-one Monero miner

GH_ACCOUNT =	fireice-uk
GH_PROJECT =	xmr-stak
GH_TAGNAME =	2.4.3

CATEGORIES =	net

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} c crypto m microhttpd ssl

MODULES =	devel/cmake
LIB_DEPENDS =	www/libmicrohttpd

CONFIGURE_ARGS =	-DCUDA_ENABLE=OFF \
			-DOpenCL_ENABLE=OFF \
			-DHWLOC_ENABLE=OFF

NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/bin/xmr-stak ${PREFIX}/bin

.include <bsd.port.mk>
