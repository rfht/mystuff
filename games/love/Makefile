# $OpenBSD: Makefile,v 1.15 2015/09/22 18:47:52 pascal Exp $

COMMENT=		2D games framework for use with Lua

V =			0.10.0
DISTNAME=		love-$V-linux-src
PKGNAME=		love-$V

SHARED_LIBS +=  love                      0.0 # 0.0

HOMEPAGE =		https://love2d.org/

CATEGORIES=		games lang/lua

# code: zlib license
# docs: freebsd license
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += luajit-${MODLUA_VERSION}
WANTLIB += SDL2 c freetype m modplug mpg123 ogg openal physfs pthread sndio
WANTLIB += theoradec usbhid vorbis vorbisfile z

MASTER_SITES=		https://bitbucket.org/rude/love/downloads/

MODULES =		lang/lua
#MODGCC4_LANGS =		c c++
#MODGCC4_ARCHS =		*

LIB_DEPENDS=		audio/libmodplug \
			audio/mpg123 \
			audio/openal \
			audio/libvorbis \
			devel/physfs \
			devel/sdl2 \
			lang/luajit \
			multimedia/libtheora
RUN_DEPENDS =		devel/desktop-file-utils \
			misc/shared-mime-info \
			x11/gtk+3,-guic

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS +=	--with-luaversion=${MODLUA_DEP_VERSION}

WRKDIST=		${WRKDIR}/love-$V

CONFIGURE_ENV=          CPPFLAGS="-I${LOCALBASE}/include -I${LOCALBASE}/include/SDL/ \
				-I${X11BASE}/include/ -I${X11BASE}/include/freetype2 \
				`pkg-config --cflags ${MODLUA_DEP}`" \
			LDFLAGS="-L${X11BASE}/lib -L${LOCALBASE}/lib -pthread"

.include <bsd.port.mk>
