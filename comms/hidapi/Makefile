# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

COMMENT =	library for communicating with USB and Bluetooth HID devices

V =	20160128
DISTNAME =	hidapi-${V}

GH_ACCOUNT =	signal11
GH_PROJECT =	hidapi
GH_COMMIT =	a6a622ffb680c55da0de787ff93b80280498330f

SHARED_LIBS +=  hidapi-libusb               0.0      # 0.0

CATEGORIES =	comms

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# GPLv3, BSD-style, or more liberal original HIDAPI license
# chosen at the discretion of the user of HIDAPI
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

BUILD_DEPENDS =	${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS}

# devel/fox is dependency for --enable-testgui
LIB_DEPENDS =		converters/libiconv \
			devel/fox \
			devel/libusb1

SEPARATE_BUILD =	simple
CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS+=	--enable-testgui
CONFIGURE_ENV =	CPPFLAGS="-I${LOCALBASE}/include/libusb-1.0 -I${LOCALBASE}/include" \
		CXXFLAGS="-O0 -pipe -g -L${LOCALBASE}/lib -lusb-1.0 -liconv" \
		CFLAGS="-O0 -pipe -g"

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

NO_TEST =		Yes

pre-configure:
	cd ${WRKSRC} && env -i \
		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} \
		autoreconf -fi
post-install:
	cd ${PREFIX}/lib && \
		ln -sf libhidapi-libusb.so.${LIBhidapi-libusb_VERSION} \
			libhdapi.so.{LIBhidapi-libusb_VERSION}

.include <bsd.port.mk>
