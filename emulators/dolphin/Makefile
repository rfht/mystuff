# $OpenBSD: Makefile.template,v 1.72 2015/04/08 17:53:19 sthen Exp $

# TODO:
# - remove audio/soundtouch dependency if using builtin
# - double check license
# - use Qt?
# - who maintainer?
# - recheck wantlib etc
# - compare against Makefile.template because taken from pre-existing port
# - needs this?: -DCMAKE_EXE_LINKER_FLAGS='-z wxneeded'
# - double-check if all the dependencies still needed
# - add /usr/local/include to include_directories?
# - add comms/hidapi to dependencies if hidapi is imported first?
# - "Nobody on the project really cares about stable releases. It's too much
#   of a burden to care" (HdkR on #dolphin-emu)
# - LIB_DEPENDS x11/qt5/qtbase,-main not needed for emulators/dolphin ?
# - version number 0.DATE versus just DATE??

USE_WXNEEDED =		Yes

ONLY_FOR_ARCHS =	amd64

COMMENT=		Nintendo GameCube and Wii emulator

V =			0.20180430
DISTNAME =		dolphin-emu-${V}
PKGNAME=		dolphin-${V}

CATEGORIES =		emulators

HOMEPAGE =		https://dolphin-emu.org/

MAINTAINER =		Anthony J. Bentley <anthony@anjbe.name>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		GL GLU ICE SDL2 SM X11 Xext Xi Xrandr ao \
			atk-1.0 avcodec avformat avutil c cairo curl \
			gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glib-2.0 \
			gmodule-2.0 gobject-2.0 gthread-2.0 gtk-x11-2.0 iconv \
			lzo2 m mbedcrypto mbedtls mbedx509 miniupnpc openal \
			pango-1.0 pangocairo-1.0 pangoft2-1.0 pangoxft-1.0 \
			png portaudio pthread pulse sfml-network sfml-system \
			swscale usb-1.0 z ${COMPILER_LIBCXX}

GH_ACCOUNT =		dolphin-emu
GH_PROJECT =		dolphin
GH_COMMIT =		ad098283c023b0f5f0d314c646bc5d5756c35e3d

MODULES =		devel/cmake \
			x11/qt5
LIB_DEPENDS=		archivers/lzo2 \
			audio/libao \
			audio/openal \
			audio/portaudio-svn \
			audio/pulseaudio \
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
			-DCMAKE_EXE_LINKER_FLAGS="-z wxneeded" \
			-DENABLE_ALSA=OFF \
			-DENABLE_WX=OFF \
			-DQt5_DIR="${LOCALBASE}/lib/qt5/cmake/Qt5"

.include <bsd.port.mk>
