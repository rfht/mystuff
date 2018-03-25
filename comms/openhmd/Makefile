# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	portable API and drivers for immersive technology

V =	20180321
DISTNAME =	openhmd-${V}
#PKGNAME =	???

#GH_ACCOUNT =	OpenHMD
GH_ACCOUNT =	ChristophHaag
GH_PROJECT =	OpenHMD
GH_COMMIT =	dev-osvr-hdk2-master/985c97f7933bb257d494e4cf4a338773161dd9e7

#SHARED_LIBS =	???

CATEGORIES =	comms

#HOMEPAGE =	???	URL

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# BSL-1.0
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =		devel/cmake
LIB_DEPENDS =		comms/hidapi

CONFIGURE_ARGS =	-DOPENHMD_EXAMPLE_SDL=ON

#NO_TEST =		Yes

WRKDIST =		${WRKDIR}/OpenHMD-dev-osvr-hdk2-master

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

.include <bsd.port.mk>
