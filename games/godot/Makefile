# $OpenBSD: Makefile.template,v 1.72 2015/04/08 17:53:19 sthen Exp $

# TODO:
# - make hardcoded binary path portable with localbase
# - double-check license

COMMENT =		2D and 3D game engine

V =			3.0.2
DISTNAME =		godot-$V

CATEGORIES =		games

HOMEPAGE =		https://godotengine.org/

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += GL X11 Xau Xcursor Xdmcp Xext Xfixes Xi Xinerama Xrandr
WANTLIB += Xrender c crypto enet execinfo freetype intl m mpcdec
WANTLIB += ogg opus opusfile png pulse pulse-simple ssl theora
WANTLIB += theoradec vorbis vorbisfile webp xcb z

GH_ACCOUNT =		godotengine
GH_PROJECT =		godot
GH_TAGNAME =		$V-stable

MODULES =		devel/scons
MODSCONS_FLAGS =	LINKFLAGS="-lintl -lmpcdec" \
			builtin_enet=no \
			builtin_freetype=no \
			builtin_glew=no \
			builtin_libmpcdec=no \
			builtin_libogg=no \
			builtin_libpng=no \
			builtin_libtheora=no \
			builtin_libvorbis=no \
			builtin_libwebp=no \
			builtin_openssl=no \
			builtin_opus=no \
			builtin_zlib=no \
			platform=x11 \
			progress=no \
			use_llvm=yes \
			verbose=yes
LIB_DEPENDS =		audio/musepack \
			audio/opusfile \
			audio/pulseaudio \
			devel/gettext \
			graphics/libwebp \
			graphics/png \
			multimedia/libtheora \
			net/enet

NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/bin/godot.x11.tools.* \
		${PREFIX}/bin/godot

.include <bsd.port.mk>
