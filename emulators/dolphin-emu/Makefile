# $OpenBSD: Makefile.template,v 1.72 2015/04/08 17:53:19 sthen Exp $

ONLY_FOR_ARCHS =	amd64

COMMENT=		Nintendo GameCube and Wii emulator

V =			20180318
DISTNAME =		dolphin-emu-${V}
PKGNAME=		dolphin-emu-${V}

CATEGORIES =		emulators

HOMEPAGE =		https://dolphin-emu.org/

MAINTAINER =		Anthony J. Bentley <anthony@anjbe.name>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		GL GLU ICE SDL2 SM SoundTouch X11 Xext Xi Xrandr ao \
			atk-1.0 avcodec avformat avutil c cairo curl \
			gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glib-2.0 \
			gmodule-2.0 gobject-2.0 gthread-2.0 gtk-x11-2.0 iconv \
			lzo2 m mbedcrypto mbedtls mbedx509 miniupnpc openal \
			pango-1.0 pangocairo-1.0 pangoft2-1.0 pangoxft-1.0 \
			png portaudio pthread pulse sfml-network sfml-system \
			swscale usb-1.0 z ${COMPILER_LIBCXX}

GH_ACCOUNT =		dolphin-emu
GH_PROJECT =		dolphin
GH_COMMIT =		0c128f3abe3f261db88b4986ec4e8dedf85b5d9c

MODULES =		devel/cmake
LIB_DEPENDS=		archivers/lzo2 \
			audio/libao \
			audio/openal \
			audio/portaudio-svn \
			audio/pulseaudio \
			audio/soundtouch \
			converters/libiconv \
			devel/libusb1 \
			devel/sdl2 \
			graphics/ffmpeg \
			graphics/png \
			multimedia/sfml \
			net/curl \
			net/miniupnp/miniupnpc \
			security/polarssl \
			x11/gtk+2

CONFIGURE_ARGS +=	-Dmandir:=${PREFIX}/man \
			-DENABLE_WX=OFF \
			-DENABLE_QT2=False \
			-DENABLE_PULSEAUDIO=OFF \
			-DENABLE_ALSA=OFF \
			-DCMAKE_EXE_LINKER_FLAGS='-z wxneeded'

USE_WXNEEDED =	Yes

.include <bsd.port.mk>
